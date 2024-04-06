>[!def]
In Haskell, a *type signature* of a function or variable is defined using a double colon (`::`).
> ```haskell
> f :: Integer -> Integer
> f x = 2 * x
> 
> f (2 + 3)
> ```
> 
> ```
> 8
> ```
> 
> To define a function with multiple inputs, chain together more of these types.
> ```haskell
> f :: Integer -> Float -> String
> f x y = show (x * y)
> 
> putStrLn (f 3 4.2)
> ```
> 
> ```
> 12.6
> ```

