>[!remark]
>Lambda calculus uses variables, which behave more similarly to those in mathematics than those in most programming languages

The symbol $\lambda$ begins a function that takes input (single variable only). The general structure is $\lambda\text{ (variable\_name) (rest\_of\_program)}$. The lambda indicates that the function is awaiting an input.
$$\begin{align*}
\lambda\ x.\ x+3
\end{align*}$$
>[!note]
>This is missing many features that might seem required for a model of computation:
>- function names
>- numbers, booleans, strings, etc.
>- sums
>- datatypes
>- multivariable functions.
>
>However, these concepts can be encoded in lambda calculus.

# Syntax
Using an inductive *grammar* definition, a lambda's syntax is defined as follows.
$$\begin{align*}
&\text{For an arbitrary lambda program, }A,\\
A ::&= x\\
&|\ \lambda x.A\\
&|\ A\ A
\end{align*}$$
- Application is **left-associative**, i.e.,
$$\begin{align*}
A\ B\ C &= (A\ B)\ C
\end{align*}$$
- Scopes of abstractions extend as far as possible to the right, i.e.,
$$\begin{align*}\lambda x.A\ B = \lambda x.(A\ B)\end{align*}$$

# Computation
To execute a program, we perform $\beta$-reduction.
$$\begin{align*}
(\lambda x.\ A)\ B \rightarrow A\ [x := B]
\end{align*}$$
This is to say, we substitute our inputs for abstracted variables.
$$\begin{align*}
(\lambda x.\ x+3)\ 2 \rightarrow (x+3)\ [x := 2] = 2+3\\\\
(\lambda x.\ x+3)\ (4\times 5) \rightarrow (x+3)\ [x := 4\times 5] = (4\times 5)+3\\
\end{align*}$$
>[!warning]
>We use `+` here, but we have not actually defined it. This can however be encoded in the lambda calculus.

## Free variables
By an inductive definition,
$$\begin{align*}
FV(x) &= \left\{x\right\}\\
FV(\lambda x.\ A) &= FV(A) - \left\{x\right\}\\
FV(A\ B) &= FV(A)\cup FV(B)
\end{align*}$$
This is to say, free variables are variables that are not bound to a $\lambda$.

>[!def]
>A term is *closed*, or a *combinator*, if it has no free variables.

>[!def]
>A variable that appears, but is not free, is said to be *bound*.

## Alpha Conversion
>[!def]
>Terms are $\alpha$-equivalent if they differ only uniformly in their bound variables.

I.e., if we have a program and change a free variable, then the program is fundamentally changed. However, if we have a bound variable, then we could rename all occurrences of the variable and the program would be equivalent to how it was before. The two programs are called *alpha equivalent*.

$$\begin{align*}
\lambda x.\ A &= \lambda y.\ A\ [x:=y]\\
\lambda x.x z &= \lambda y.y z \ne \lambda z.z z\\
(\lambda y.\lambda z.y)\ z &= (\lambda w. \lambda y.w)\ y\ne (\lambda y.\lambda w.w)\ y
\end{align*}$$

## Reusing Bound Variables
Clearly `lx.lx.x = ly.ly.y`, but what about `ly.lx.y` or `lx.ly.y`?

Variables are bound by the innermost $\lambda$.

## Substitution
Suppose we would like to substitute a "value" for a variable `x`.
- `x[x:=A] = A`
- `y[x:=A] = y` if `y != x`
- `(B C)[x:=A] = (B[x:=A]) (C[x:=A])`
- `(ly.B)[x:=A] = ly.B[x:=A]` if `y != x` and `y not in FV(A)`
	- If this side condition fails, then we must rename `y` using $\alpha$-conversion to something that is neither $x$ nor any free variable.

Without the second side condition on the last case, then,
- `(lx.y)[y:=x] = lx.x`
- `(lz.y)[y:=x] = lz.x`
However, these two program began as the same program, and became different programs - the `x` was captured by the $\lambda$ in the first case. Therefore we must take special consideration of the free variable `y`.
In this case, the first is incorrect! As `x` was in the free variables of `x`, the substitution, then we must first rename `lx` to something like `lk` and create the program `lk.x`.

## Simple Programs
- The identity, `lx.x`; `(lx.x) A = A`
- `lx.A` (with `x` not in `FV(A)`) ignores the input and outputs `A`; `(lx.A) B = A`

## Functions With More Than One Input
A function with two or more inputs can be captured by stacking lambdas.
`lx.ly.x+y`
Treating such a function with multiple inputs as a sequence of single-input functions is called *currying*.

## Booleans
>[!question]
>How could we encode booleans?

To do this, we would need a combinator for `True`, another for `False`, and another for `if .. then .. else ..` so that:
- `if True then A else B ->> A`
- `if False then A else B ->> B`

>[!note]
>`->>` here signifies 'one or more beta reductions'.

We will encode:
- `True` as `lx.ly.x` (*take two inputs and return the first*)
- `False` as `lx.ly.y` (*take two inputs and return the second*)
- `if..then..else` as `lx.ly.lz. x y z` (*take x and apply it to y and z*)

This can be shown to work.

>[!remark]
>This has no types! Types typically don't affect computation, and so aren't in the most bare-bones form of the lambda calculus.
>This means that seemingly invalid programs such as `if (lx.x) then True else (lx.y)` are in fact valid, though may have unintended behaviour.

# Pairs
We can encode:
- `<A,B>` pairs as `lx. if x then A else B`
- fst as `lx.x True`
- snd as `l.x False`

```
fst <A,B>
->  (lx.x True) (lx. if x then A else B)
->  (lx. if x then A else B) True
->  if True then A else B
->> A

snd <A,B>
->  (lx.x False) (lx. if x then A else B)
->  (lx. if x then A else B) False
->  if False then A else B
->> B
```

# Barendregt Natural Numbers
We encode:
- `0` as `lx.x`
- `n+1` as `<False,n>`
- `isZero` as `lx.x True` (`fst`)
- `succ` as `lx.<False, x>`
- `pred` as `lx.x False`

```
isZero 0
->  (lx.x True) lx.x
->  lx.x True
->  True

isZero 1
->  (lx.x True) <False, lx.x>
==  fst <False, lx.x>
->  False

2
->  <False, <False, lx.x>>

succ 2
->  lx. <False, <False, lx.x>> False
->  
```

# Church Natural Numbers
We encode:
- `0` as `lx.ly.y`
- `n+1` as `lx.ly.(apply x n times to y)`
- `isZero` as `lz.z (ly. False) True`
- `succ` as `lz.lx.ly.x (z x y)`
- `pred` as `(complicated)` (`pred 0 ->> 0`)

# Scott Natural Numbers
We encode:
- `0` as `lx.ly.x` (`False`)
- `n+1` as `lx.ly.y n`
- `isZero` as `lz.z True (lx. False)`
- `succ` as `lz.lx.ly.y z`
- `pred` as `lz.z 0 (lx.x)` (`pred 0 ->> 0`)

# Recursion
From the successor and predecessor, we can encode `+, *, ^` by finding a way to do recursion.

```
greaterOrEq = lx.ly.if (isZero x) then (isZero y) else (greaterOrEq (pred x) (pred y))
```
This recursively reduces the numbers `x` and `y` until `x` is zero, at which point it is trivial to find which was greater using `isZero`, using the fact that `pred 0 ->> 0`.


## Fixed-point Combinators
Suppose there was a combinator `Z` such that `Z F ->> F (Z F)`.
This would mean that `Z` could repeatedly apply a function `F`, and as long as `F` has a base case it may terminate.

Such a combinator is called a *fixed point combinator*.
```
Z F ->> F (Z F) ->> F (F (Z F)) ->> ...
```

### example usage
For example, to do `greaterOrEq` with a fixed-point combinator, we could do the following:
```
G := lg.lx.ly if (isZero x) then (isZero y) else g (pred x) (pred y)

>   Z G 0 0
->> G (Z G) 0 0
->> if (isZero 0) then (isZero 0) else g (pred 0) (pred 0)
->> True
Correct!

>   Z G 0 1
->> G (Z G) 0 1
->> if (isZero 0) then (isZero 1) else g (pred 0) (pred 0)
->> False
Correct!

>   Z G 2 1
->> G (Z G) 2 1
->> if (isZero 2) then (isZero 1) else (Z G (pred 2) (pred 1))
->> Z G (pred 2) (pred 1)
->> Z G 1 0
->> G (Z G) 1 0
->> if (isZero 1) then (isZero 0) else (Z G (pred 1) (pred 0))
->> Z G 0 0
->> True
Correct!

>   Z G 1 2
->> G (Z G) 1 2
TODO

```
### Turing's fixed-point combinator
Such a combinator exists!
```
let A = lx.ly.y(x x y)
    t = A A

Then, t -> ly.y(A A y) -> ly.y(t y)
So, t F -> ( ly.y(t y) ) F -> F (t F)
```

# Termination
>[!def]
>A term is said to be in *normal form* if it cannot be reduced any further

It is possible to make lambda program that never terminate.
```
(lx.x x)(lx.x x) -> (lx.x x)(lx.x x)
```

Some programs may terminate or not terminate depending on the order of beta reduction.
```
(ly.z)((lx.x x)(lx.x x)) -> z
(ly.z)((lx.x x)(lx.x x)) -> (ly.z)((lx.x x)(lx.x x))
```

The problem of deciding the order of beta reduction is called *evaluation order*.

>[!question]
>Can multiple different inputs be reached if the program is certainly non-terminating?

Consider the following.
```
lx.(ly.y) x ((lz.w) x) -> lx.x ((lx.w) x) -> lx. w
lx.(ly.y) x ((lz.w) x) -> lx.(ly.y) x w -> lx.x w
```

>[!theorem]
>The *Church-Rosser* property (aka confluence) states that if `A->>B` and `A->>C` then there exists `D` such that `B->>D` and `C->>D`. So a terminating program must terminate in the same state regardless of evaluation order.

>[!cor]
>If a term has a normal form, then it has exactly one normal form.

# $\beta$-Equality
Two terms are beta-equal, written $=_{\beta}$, if they are related by the *symmetric closure* of `->>`.
So `A ->> B <<- C ->> D <<- ... Z` means that `A =b Z`.
One way to do this is to check if their reduced normal forms match. This can't be done if they are non-terminating however.
Note that a fixed combinator requires that `F X =b X (F X)`
# The Y Combinator
`Y := lf.(lx.f(x x))(lx.f(x x))`
This is a fixed point combinator.
```
Y F = lf.(lx.f(x x))(lx.f(x x)) F
  ->> (lf.F(x x))(lx.F(x x))
  ->> TODO
```

# Big Step Operational Semantics
```
(lx.A) B  ->> A[x:=B]

if      A ->> A'
then lx.A ->> lx.A'

if      A ->> A'
then  A B ->> A' B

if      B ->> B'
then  A B ->> A B'
```

Note that the above states lambda calculus in a non-deterministic form, as we may choose the order in which to apply reductions.

Consider `(lx.A)B`
- As Haskell is lazy, it will first do top-level reduction, so `(lx.A)B ->> A`.
- Most languages will instead do strict evaluation, where `B` is evaluated first. So `(lx.A)B ->> (lx.A)B'`.

## Lazy Operation Semantics
```
if     A ->> lx.A', A'[x:=B] ->> C,
then A B ->> C
```

Note that in this scheme, we cannot reduce a term of the form `lx.A`. So this will be a normal form. Note also that this means normal forms differ depending on the evaluation strategy being implemented.
## Strict Operation Semantics
```
if   A ->> lx.A', B ->> B', A'[x:=B'] ->> C
then            A B ->> C
```

Once again, `lx.A` will not reduce any further and is therefore a normal form.

## Comparison
```
Lazy:
(lx.x x)((ly.y) z) -> (ly.y) z ((ly.y) z)
                   -> z ((ly.y) z)

Strict:
(lx.x x)((ly.y) z) -> (lx.x x) z
				   -> z z
```