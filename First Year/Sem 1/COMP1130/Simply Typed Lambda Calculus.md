# Curry and Church's Definition 
By Curry's definition, `lx.x` has many types.
By Church's definition, `lx.x` must be annotated, e.g., `lx:Bool.x`, `lx:(Nat -> Bool).x`.
We will be using Curry's definition.

# Principal Types
A Curry-style term may have many types, and has at most one *principal type* (usually written $\alpha$). This is related to parametric polymorphism.
E.g., the principal type of `lx.x` is $\alpha \rightarrow \alpha$.

Types are defined recursively as:
```
t ::= a | b | t -> t
e.g., a -> b -> a
```

# Type Judgements
We write $\vdash$ `A : t` (`T A : t`) to mean "`A` has type `t`".
A *basis* $\Gamma$ (`G`) is a finite set of distinct variable attached to types.
$\Gamma\vdash$`A : t` means "`A` has type t if its free variables have types as in $\Gamma$". (`GT A : t`).

```
---
G, x : t T x : t

G, x : s T A : t
GT lx.A : s -> t

GT A : s -> t GT B : s
GT A B : t
```

# Finite Base Types
