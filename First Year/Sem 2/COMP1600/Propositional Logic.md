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

>[!remark]
>Note the following:
>$p \rightarrow q = \neg p \lor q$
>$p \lor q = \neg(\neg p \land \neg q)$

>[!def]
>A *subformula* is a formula that appears in another formula.
>All formulae are subformulae of themselves.
>>[!example]
>>$\text{subf}(p) = \left\{p\right\}$
>>$\text{subf}(A\land B) = \left\{A\land B\right\}\cup\left\{A\right\}\cup\left\{B\right\}$
>
>We may say that $A$ is 'simpler' than $B$ to mean that $A\in\text{subf}(B)$.

>[!def]
>A *truth table* is a table where each column is a subformula of a particular formula, and where the rows represent all possible variable assignments to the variables in the formula.
>Additionally, the subformulae of a column label all appear to its left.
>Because of this, the rightmost label represents the entire formula.
> 
>>[!example] 
>> | $p$   | $q$   | $q\land p$ | $q \land p \rightarrow  q$ | $p \rightarrow  q \land p \rightarrow  q$ |
>> | --- | --- | ----- | ---------- | --------------- |
>> | $\top$   | $\top$   | $\top$     | $\top$          | $\top$               |
>> | $\top$   | $\bot$   | $\bot$     | $\top$          | $\top$               |
>> | $\bot$   | $\top$   | $\bot$     | $\top$          | $\top$               |
>> | $\bot$   | $\bot$   | $\bot$     | $\top$          | $\top$               |
>> So the formula is a tautology, $\vdash p \rightarrow q \land p \rightarrow q$.
>
>>[!remark]
>>A truth table with $n$ variables has $2^{n}$ rows. So a formula with no variables has one row.
>>>[!proof]
>>> 
>>> By induction.
>>> **Base case.**
>>> For $n=0$, there is one row.
>>> **Inductive step.**
>>> Suppose that for all $n<k$, there are $2^{n}$ rows.
>>> If we let $n=k$, there are two possible values of the last variable, so we double the number of rows from the $2^{n-1}$ case.
>>> $$\tag*{$\blacksquare$}$$

>[!def]
>A *tautology* is a formula that is true under all variable assignments.
>A *contradiction* is a formula that is false under all variable assignments.
>A *contingency* is a formula which may evaluate to either true or false at least one variable assignment each.
>>[!examples]
>>$\top,\ p\lor \neg p$ are examples of tautologies.
>>$\bot,\ p\land\neg p$ are examples of contradictions.
>>$p, p\lor q$ are examples of contingencies.

>[!def]
>Two formulae are *equivalent* if they evaluate to the same value under all variable assignments.
>All contradictions are equivalent to each other, and all tautologies are equivalent to each other. No contradiction is equivalent to any tautology.
>Some contingencies are equivalent to each other, but some are not.

>[!remark]
>Logic cannot always be translated to English easily, but generally:
>- $\lor$ is similar to 'or'
>- $\land$ is similar to 'and'
>- $\neg$ is similar to 'not'
>- $\rightarrow$ is similar to 'if ... then ...'
>>[!example]
>>
>>This is difficult to translate to English in a neat way.
>>$$\begin{align*}
>> (a \rightarrow c)\lor(b \rightarrow c)
>> &= (\neg a\lor c)\lor(\neg b\lor c)\\
>> &= \neg a\lor \neg b\lor c\\
>> &= \neg(a\land b)\lor c\\
>> &= a\land b \rightarrow c
>> \end{align*}$$

>[!theorem]
>The question, 'is $A$ a tautology?' is decidable.
>>[!proof]
>>We may simply generate the truth table $A$ by induction, and then check the right-hand column.

# Useful Laws
- $p\land q = q\land p$
- $\neg\neg p = p$
- $p \rightarrow q = \neg p \lor q$
- $\neg(p \rightarrow q) = p \land \neg q$
- de Morgan laws:
	- $\neg(p\lor q) = \neg p\land \neg q$
	- $\neg(p\land q) = \neg p\lor \neg q$

>[!remark]
>We can express two formulae as being equivalent through a propositional formula.
>$$\begin{align*}
>(A \rightarrow B)\land (B \rightarrow A)
>\end{align*}$$

>[!lemma]
>$A$ and $B$ are equivalent if and only if
>$$\begin{align*}
>(A \rightarrow B)\land (B \rightarrow A)
>\end{align*}$$
>is a tautology.

>[!remark]
>We can interpret a truth table as a boolean function $f : \mathbb{B}^{n} \rightarrow \mathbb{B}$ for a formula with $n$ variables.

>[!theorem]
>For every $f : \mathbb{B}^{n} \longrightarrow \mathbb{B}$ there is a formula $A$ in the variables $\left\{p_{1},p_{2},\cdots,p_{n}\right\}$ such that $f=f_{A}$.
>I.e., there is a bijection between the set of formulae (identified by their equivalence) and the set of all boolean functions $\mathbb{B}^{n}\rightarrow \mathbb{B}$.

>[!question]
>How many possible boolean function are there in $n$ variables?
>How many are possible if only allowing $\bot$ and $\lor$?
>>[!solution]
>>The number of boolean functions possible is $2^{2^{n}}$.
>>If we only have $\bot$ and $\lor$, we can only write $2^{n}$

>[!def]
>A set of connectives is *expressively complete* if all boolean functions can be expressed using connectives in that set.

>[!example]
>Is the set $\left\{\lor,\text{xor}\right\}$ expressively complete?
>This is in fact false.
>>[!proof]
>>We will find an invariant property of formulae in this set that is not true of some other connective that we should be able to encode.
>>We may note that any formula using these connectives will map to false whenever all variables are assigned false.
>>So the negation operator cannot be encoded.

