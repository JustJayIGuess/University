>[!remark]
>*Types* can be thought of as an analogue to **sets** in mathematics.

Haskell is **statically typed**, so types must be determined before the program runs. This means that type errors will appear at compile time rather than run time.

# Prelude
>[!def]
>*Prelude* is the **standard Haskell library**.

# Booleans
These are mathematically represented by the set $\mathbb{B} = \left\{\text{True}, \text{False}\right\}$.
```haskell
data Bool = False | True
```

On this type, we may define the following operators.
- `&&`, the logical 'and' operator
- `||`, the logical 'or' operator
- `not`, the logical 'not' operator

>[!note]
>Note that exclusive or is not defined in Prelude! We must define it ourselves if we want to use it.
>```haskell
>xor :: Bool -> Bool -> Bool
>xor x y = (x || y) && not (x && y)
>```


We may represent functions on Booleans using a *truth table*.

| `s` | `t` | `s && t` | `s \|\| t` | `not t` | `s xor t` |
| --- | --- | -------- | ---------- | ------- | --------- |
| 0   | 0   | 0        | 0          | 1       | 0         |
| 0   | 1   | 0        | 1          | 0       | 1         |
| 1   | 0   | 0        | 1          | 1       | 1         |
| 1   | 1   | 1        | 1          | 0       | 0         |

Relational operators return a Boolean, i.e.,
- `==` - equal to
- `/=` - not equal to
- `>` - greater than
- `>=` - greater than or equal to
- `<` - less than
- `<=` - less than or equal to

# Characters
Literal characters are written inside single quotes.
```haskell
'a', 'b', ... , 'z', 'A', ... , 'Z',
'\n', '\t', '\\', '\'', '\"'
```

# Strings
Strings are written in sequence using double quotes.
```haskell
"Hello, world!"
```

Strings may be concatenated using the `++` operator.
```haskell
"hello, " ++ "world!"
```

```
hello, world!
```

>[!remark]
>The `++` operator has a type signature of `String -> String -> String`.


# Integers
Integer represents whole numbers of any size (up to the limit of machine memory!).
There are many operators defined on the integers (see documentation for this).