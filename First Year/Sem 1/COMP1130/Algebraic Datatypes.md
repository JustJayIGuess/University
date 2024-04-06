We may tag a product and/or sum of types with a new name.
```haskell
data Accomodation = Hotel String Double Double
					| Hostel String Int Double
					| Airbnb String Double
					| Friend String
```

# The `Maybe` Datatype
`Maybe` is defined in Prelude.
```haskell
data Maybe Int = Just Int | Nothing
```
For example, this could be used to implement a safe division between `Int`s; if a division by zero occurs, then the value `Nothing` can be returned.

