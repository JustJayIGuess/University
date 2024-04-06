# Pattern Matching
>[!def]
>This is for dealing with **sum types**, which list the different ways that a type may be constructed, each with a unique tag name and separated with `|`.
>If a function takes in a sum type as input, or constructs a sum type during its execution, it will almost always need to act differently on different constructors.
>The Haskell expression *case* allows us to *pattern match* the different possible constructors.

```haskell
data Bool = True | False

myNot :: Bool -> Bool

myNot b = case b of
	True -> False
	False -> True
```

>[!note]
>This code is not good code, but rather just a simple example of the `case` syntax.

The pattern matching may be on a new type created through an operation on an input.
```haskell
data Bool = True | False

myAbs :: Int -> Int

myAbs x = case x >= 0 of
	True -> x
	False -> -x
```

One can also pattern match on a tuple.
```haskell
data Bool = True | False

myAnd :: Bool -> Bool -> Bool

myBool a b = case (a,b) of
	(False, False) -> False
	(False, True) -> False
	(True, False) -> False
	(True, True) -> True
```

In this case, all possibilities map to `False` except for `(True, True) -> True`, so this code can be simplified as follows.
```haskell
data Bool = True | False

myAnd :: Bool -> Bool -> Bool

myAnd a b = case(a,b) of
	(True, True) -> True
	_            -> False
```

>[!warning]
>Haskell runs cases from top down, so if the last two lines in the above program were switched, then `myAnd` would **always** return `False`!

>[!example]
>```haskell
>-- Millipede has a piece of data corresponding to the number of body segments.
>data Animal = Cat | Chickenrat | Worm | Millipede Int | Octopus
>
>countLegs :: Animal -> Int
>countLegs a = case a of
>	Cat                -> 4
>	Chickenrat         -> 2
>	Worm               -> 0
>	Millipede segments -> segments * 2
>	Octopus            -> error "but do octopuses have legs though??"
>```

# Guarded Expressions
Doing cases on a `Bool` has a special syntactic sugar that may be used, called *guarded expression*. These are not needed, but are preferred for readability.

>[!error] Without guarded expression

```haskell
myAbs :: Int -> Int
myAbs x = case x >= 0 of
	True -> x
	False -> -x
```

>[!check] With guarded expression

```haskell
myAbs x
	| x >= 0    = x
	| otherwise = -x
```

>[!remark]
>Every `otherwise`