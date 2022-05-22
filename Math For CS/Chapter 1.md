# What is a Proof?

### Prepositions

***Definitions***: A _preposition_ is a statement that is either true or false.

There's an important symbol that's been mentioned in the footnote: 

> The symbol `::=` means _“equal by definition.”_ It’s always ok simply to write `=` instead of `::=`, but reminding the reader that an equality holds by definition can be helpful.

#### Claim 1.1.3
This claim states: _For every positive integer $n$ the value of $n^2 + n + 41$ is a prime_.

This, in itself is a simple proposition, we can check if it's true by the use of a proof.
If simple numerical experimentation is used, this seems to be a plausible claim, however, it's not until we try $n=40$ that we run into a contradiction:

if $p(n) ::= n^2 + n + 41$ then for $n=40$ :

$$
	p(40) = 40^2 + 40 + 41 = 41^2
$$

Which, in fact, is not prime. Hence the proposition (**Claim 1.1.3**) is false.

Propositions like this about all numbers or all items of some kind are so common that there is a special notation for them. For instance, if we want to use said notation for **Claim 1.1.3**, it would be like so:

$$
	\forall n \in \mathbb{N}.\ p(n)\ is\ prime
$$

Here, the symbol $\forall$ is read as _"for all"_. The symbol $\mathbb{N}$ represents the set of all natural numbers. The symbol $\in$ is read as _"A member of"_, or _"belongs to"_, or simply _"is in"_. The period between the statements just acts as a seperator.

#### Proposition 1.1.4

This proposition states: _Every map can be colored with 4 colors so that adjacent 2 regions have different colors._

NOTE: This proposition is famously knows as **Fermat's Last Theorem**,


TODO: add this to a git repo
TODO:  add a bibliography with links to books.

