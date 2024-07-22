>[!def]
>A *propositional formula* is something where it makes sense to ask if it is true.
>If $V$ is a set of variables, then:
>- $\top,\bot$  are propositional formulae
>	- $\top$ is always true, $\bot$ is always false
>- every variable $p\in V$ is a propositional formula
>- if $A,B$ are propositional formulae, then so are $A\land B$, $A\lor B$ and $A\rightarrow B$
>	- $\land$ represents logical 'and', and $\lor$ represents logical 'or'
>	- $\rightarrow$ represents implication.
>- if $A$ is a propositional formula, then $\neg A$ also is.
>	- $\neg$ represents logical negation.

>[!remark]
>$p\land q\lor r$ can mean either:
>- $p\land (q\lor r)$, or
>- $(p\land q)\lor r$.
>
>These represent distinct propositional formulae.
>Parentheses should be used to clarify the intended reading.
>Otherwise, the standard order of precedence, in order of highest priority to lowest is:
>- $\neg$
>- $\land$
>- $\lor$
>- $\rightarrow$
>
>Otherwise, we apply right-associativity, so that $A\rightarrow B\rightarrow C$ is read as $A\rightarrow (B\rightarrow C)$.

>[!def]
>A *variable assignment* is a mapping $\sigma : V \longrightarrow \left\{\top, \bot\right\}$. If an assignment $\sigma$ is given:
>- $\top$ is always true, $\bot$ is always false
>- $p$ is true if $\sigma(p)$ is true
>- $A\land B$ is true if both $A$ and $B$ are true
>- $A\lor B$ is true if at least one of $A,B$ are true
>- $A\rightarrow B$ is true if either $A$ is false or $B$ is true (inclusive)
>	- So, $A\rightarrow B = \neg A \lor B$
>- $\neg A$ is true if $A$ is not true
>
>We write $\sigma \vdash A$ if $A$ is true under the assignment $\sigma$, and say that '$A$ is true under $\sigma$'. We say that $A$ is a 'tautology' if $A$ is true under all variable assignments, which is written $\vdash A$.

