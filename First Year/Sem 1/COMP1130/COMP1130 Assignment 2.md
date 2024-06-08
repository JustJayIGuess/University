>[!info] 
>Jay Johnston, u7922560
>Tuesday 6pm-8pm Lab with Linda Kwan and Peter Oslington

<div style="page-break-after: always;"></div>

# Introduction
This Haskell program implements two cellular automata: HighLife and a custom cellular automaton. The `.` key allows the user to advance the automaton by one step, and the `-` and `+` keys can change the size of a 'jump', allowing users to advance by multiple steps at once by pressing `<space>`.
The custom automaton simulates clouds over a generated landscape. The user can switch to this option by pressing the `J` key, and the `H` key will switch back to HighLife. The custom automaton begins in a noisy state, but reaches a stable state after ~50 steps.
Keys `1-3` will switch through different example initial states for the HighLife automaton, and `4-6` will switch through examples for the custom automaton.

# Program Design
The program uses a model-view-controller paradigm, with a `Model` representing the state of the program, a number of functions defining how this state should be visualised, and a number of functions defining how the state should be updated.
This structure is well suited to functional languages such as Haskell.

The program can switch between two main modes, one where the default HighLife cellular automaton is run, and one where the custom cellular automaton is run. As only these two are implemented, and no additional automata are expected to be added, the functions specific HighLife were duplicated and reimplemented to follow the rules of the custom automaton. This made the code easier to test and maintain and avoided unnecessary complexity.

## Datatypes / Model
The following datatypes were defined to represent the state of the program at any time.

### `Condition`
```haskell
data Condition = Dead | Alive
  deriving (Eq, Show)
```

`Condition` tracks whether a cell is alive or dead, and is used to represent cells in the `HighLife` automaton.

### `AltCondition`
```haskell
data AltCondition = Sky Int | Ground Int | Cloud Int Int
  deriving (Eq, Show)
```

`AltCondition` tracks the state of a cell in the custom automaton, which is either a `Sky` tile with an `Int` humidity value, a `Ground` tile with an `Int` tracking the number of surrounding `Sky`s, or a `Cloud` tile with an `Int` age and an `Int` tracking the number of surrounding `Sky`s.

### `Model`
```haskell
data Model = Model Int Int (Grid Condition) (Grid AltCondition) (CAStack AreaCoord) Bool
```

`Model` was changed from the original implementation to hold both a `Grid Condition` and `Grid AltCondition` to allow for switching between the HighLife automaton and the custom automaton. The ending `Bool` parameter is `True` when the custom automaton is being used, and `False` otherwise.

## Rendering Logic / View
```haskell
render :: Model -> Picture
renderGrid :: Grid Condition -> (Grid Condition -> Condition -> Picture) -> Picture
altRenderGrid :: Grid AltCondition -> (Grid AltCondition -> AltCondition -> Picture) -> Picture
```

`renderGrid` and `altRenderGrid` are called by `render` in `App.hs`, which is in turn called by codeworld through `activityOf`. `renderGrid` and `altRenderGrid` are responsible for converting a given `Grid` into a codeworld `Picture` to be displayed, given a way to render any one cell.

As codeworld `Picture` does not derive `Eq,Show`, no tests were made for these functions in `AutomataTest.hs`. These functions were instead tested by running the program and ensuring that the output's appearance was as expected.

```haskell
renderArea :: Grid a -> Condition -> Picture
altRenderArea :: Grid a -> AltCondition -> Picture
getCellDimensions :: Grid a -> (Double, Double)
```

`renderArea` and `altRenderArea` render a single cell in a grid, given its condition.
`renderArea` simply returns a rectangle, coloured yellow if alive and blue if dead, with the correct width and height to fit the defined `paneWidth` and `paneHeight`. This correct width and height are found through the helper function, `getCellDimensions`.

As the custom automaton aims to appear like a landscape, `Ground` and `Cloud` tiles hold `Int`s representing the number of surrounding `Sky` tiles, for use in shading through `altRenderArea`.
In `Cloud`s, the number of `Sky` tiles is used to interpolate between `white` and `blue`, so that cloud tiles that are on the edge of a cloud appear more transparent.
In `Ground`s, `altRenderArea` interpolates between `dark brown` and `green`, to create the appearance of grass near the surface of the ground.

## Updating Logic / Controller
Upon receiving user input, such as a keypress or mouse click, `parseEvent` will determine the relevant `AppEvent` to apply to the model, done via `applyEvent`.
`applyEvent` was edited to allow the new `Model` datatype to be used, and the `J` key was mapped to the `loadCustom` `AppEvent`, which loads the custom automaton.

When the `.` or `<space>`  keys are pressed, the grid must be updated. The following functions are used to update `Model`'s `Grid Condition` and `Grid AltCondition` members according to the rules of HighLife and the custom automaton.

### `cycleCondition`, `altCycleCondition`, `unCycleCondition` and `altUncycleCondition`
```haskell
cycleCondition :: Condition -> Condition
uncycleCondition :: Condition -> Condition
altCycleCondition :: AltCondition -> AltCondition
altUncycleCondition :: AltCondition -> AltCondition
```

`cycleCondition` and `altCycleCondition` each cycle through the different possible `Condition`s or `AltCondition`s, and the remaining functions cycle in the opposite direction. These are called on mouse clicks or when the user requests an `Undo` action.

These functions were all exhaustively tested on all possible inputs types.

### `get`
```haskell
get :: Grid a -> AreaCoord -> Maybe a
```

`get` takes a grid and `AreaCoord` and returns a `Just` the object that was at that position if the `AreaCoord` was in bounds, and `Nothing` otherwise.
This function is polymorphic, so it is used for both the HighLife and custom automata.

`get` was tested on a sample grid. The pair of coordinates, `(3,5)` and `(5,3)`, were tested to ensure that the coordinates are being interpreted correctly. A coordinate with negative values and another with very large values were also tested to ensure that `get` returned `Nothing` when out of bounds.

### `multiSteps` and `altMultiSteps`
```haskell
multiSteps :: Grid Condition -> Int -> Grid Condition
altMultiSteps :: Grid AltCondition -> Int -> Grid AltCondition
```
`multiSteps grid n` will apply `updateGrid` to `grid` `n` times for a positive or zero integer `n`, and otherwise throw an error.
`altMultiSteps grid n` has the same implementation, but instead applies `altUpdateGrid` and operates on a `grid` of type `Grid AltCondition`.
This is called by `applyEvent` when the `<space>` key is pressed.

These functions were tested on small 3x3 grids with multiple steps to ensure that the rules were applied correctly. Additionally it was checked that stepping 0 times would leave the grid unchanged.

### `updateGrid` and `altUpdateGrid`
```haskell
updateGrid :: Grid Condition -> Grid Condition
altUpdateGrid :: Grid AltCondition -> Grid AltCondition
```

`updateGrid grid` will apply the rules of HighLife to each cell in the given `grid`, and return a `Grid` with the same number of rows and columns, and the updated cells. This is done by applying `updateSite` to the grid (using a helper function, `mapper`) at all possible coordinates, given by `allCoords`.
`altUpdateGrid grid` does the same, however it instead calls `altUpdateSite` to apply the rules of the custom automaton.

These functions were each tested on a small 3x3 grid to ensure that the automata's rules were followed correctly, and were additionally tested on a 0x0 grid to ensure that no unexpected errors occurred in such an edge case.

To avoid added complexity in validating `Grid`s any time they were used, it was assumed that the number of rows and cols in a `Grid` would always be positive.
As the number of rows and cols is always kept the same throughout the program, there are no edge cases where a grid may attain an invalid state with negative dimensions.

### `allCoords`
```haskell
allCoords :: Grid a -> [AreaCoord]
allCoordsHelper :: Grid a -> Int -> [AreaCoord]
```

`allCoords` returns a list of all possible coordinates (starting at `(0,0)`) on a grid in row-major order via a recursive helper function, `allCoordsHelper`.
This function is polymorphic, and so can be used for both the HighLife and custom automata.

This was tested on a 3x3 grid to ensure that the correct list of coordinates was returned, and in the correct row-major order.

### `updateSite`
```haskell
updateSite :: AreaCoord -> Grid Condition -> Condition
```

`updateSite` implements the core behaviour of the HighLife cellular automaton. A helper function maps `Alive` cells to `1` and `Dead` cells to `0`. Coordinates out of bounds will also map to `0`. The number of cells that are alive in the immediate neighbourhood (based on coordinates given by `nearNeighbours`) is then used to implement the rules of HighLife.

This function was tested on a 3x3 grid as a white box (updating the centre cell), with a test for each possible case in the implementation.

### `altUpdateSite`
```haskell
altUpdateSite :: AreaCoord -> Grid AltCondition -> AltCondition
```

`altUpdateSite` implements the rules of the custom automaton. As an overview, the rules are:
- `Sky` tiles increase their humidity each step
- If a `Sky` tile is sufficiently humid and near another cloud to seed it, or is to the left of a large number of a `Cloud`s, it will become a new `Cloud`
- If a `Sky` tile is on the edge of the grid and is sufficiently humid, it will become a new `Cloud`
- `Ground` tiles surrounded by mostly `Sky` tiles will become `Sky` tiles
- `Sky` tiles surrounded by mostly `Ground` tiles will become `Ground` tiles.
This function otherwise works in a similar way to `updateSite`.

As these rules were iteratively adjusted to give the desired appearance and behaviour of a landscape, it was considered sufficient to test `altUpdateSite` by stepping through the program and noting that there was no unexpected behaviour.

### `nearNeighbours` and `farNeighbours`
```haskell
nearNeighbours :: AreaCoord -> [AreaCoord]
farNeighbours :: AreaCoord -> [AreaCoord]
```

`nearNeighbours p` simply returns a list containing the coordinates of immediate neighbours of `p`. It is not required to check that these are all in bounds, as then `get` will return `Nothing` and this case is handled in `updateSite` and `altUpdateSite`.
`farNeighbours p` returns a list of the immediate neighbours of `p`, as well as the two extra columns of three cells to the right of this neighbourhood. This is needed for the custom automaton.

These functions were tested as black boxes by checking that the set of returned `AreaCoord`s were equivalent to the desired set given an arbitrary point. As the order in which the `AreaCoords` were returned was unimportant, an additional test assertion, `assertSetEquiv`, was implemented.

### `assertSetEquiv`
```haskell
assertSetEquiv :: (Eq a, Show a) => [a] -> [a] -> TestResult
```

`assertSetEquiv` returns `OK` if the two given lists are subsets of each other and neither contain any duplicates. This means that ordering does not matter, i.e., the lists are treated as sets.

This was tested by comparing a list with no duplicates to:
- another similar list with a different ordering
- an empty list
- an equivalent list with an added duplicate
- a list containing elements not in the original list.
This covered all foreseen edge cases. Testing this was especially important, as the validity of other tests relied on the soundness of this function.

# Reflection
A major issue of the program is its performance, as it quickly becomes unresponsive with larger grids. This may be due to overhead associated with drawing a large number of separate rectangles through codeworld.
Additionally, the program indexes into the list of cells for each cell on each step, resulting in a time complexity of $O(n^{2})$, and `allCoords` is called on each step despite returning the same values each time.
It may therefore be possible to improve performance by using an $O(1)$ indexing datatype such as `Data.Vector`, and caching the results of `allCoords` in the `Model`. However, without first profiling the program to find performance bottlenecks, it is not possible to determine which of these issues contribute the most to the performance cost.

The program also has many duplicated functions for each of the automata, making it more difficult to maintain if changes must be made. An approach using a polymorphic `Model` datatype may make the code easier to change and extend.
Under the assumption that no additional automata would be added, however, the current implementation avoids unneeded complexity.