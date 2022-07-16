# What is a Proof?

***Definition***: A _mathematical proof_ of a _[[#Propositions|proposition]]_ is a chain of _[[#Logical Deductions|logical deductions]]_ leading to the proposition from a base set of _[[#Axioms|axioms]]_. ([[Bibliography#^9c2cde|reference]])


### Propositions

***Definition***: A _proposition_ is a statement that is either true or false.

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

There exist several propositions whose proofs were sought for centuries before finally being discovered. Here are some examples: 

##### Proposition 1.1.4

This proposition states: _Every map can be colored with 4 colors so that adjacent 2 regions have different colors._
NOTE: This proposition is famously knows as **Four Color Theorem**.

The book specifies in a footnote:

> Two regions are adjacent only when they share a boundary segment of positive length. They are not considered to be adjacent if their boundaries meet only at a few points

Several incorrect proofs of this theorem have been published, including one that stood for 10 years. After many years, a mostly [[Four-Color-Proof.pdf|intelligible proof]] was found, though a computer us still needed to check four-colorablilty of several hundred specific maps.

##### Proposition 1.1.5

This proposition states: _There are no positive integers $x,\ y$ and $z$ such that_
$$
	x^n\ + y^n\ =\ z^n
$$
_for some integer $n\ >\ 2$_

Over the years, the Theorem was proved to hold for all $n$ up to 4,000,000, but we’ve seen that this shouldn’t necessarily inspire confidence that it holds _for all $n$_.

Finally, in 1994, British mathematician Andrew Wiles gave a proof, after seven years of working in secrecy and isolation in his attic. His proof did not fit in any margin.

##### Conjecture 1.1.6

This is a simply stated proposition whose truth remains unknown.
The conjecture states: _Every even integer greater than 2 is the sum of two primes._

This conjecture is more popularly known as **Goldbach's Conjecture**, and this dates back to 1742. It is known to hold for all numbers up to $10^{18}$, but to this day, nobody knows if this holds for all positive numbers or not.


### Predicates

***Definition***: A _predicate_ can be understood as a proposition whose truth depends on the value of one or more variables.

It is also mentioned in MFCS:

> This notation for predicates is confusingly similar to ordinary function notation. If $P$ is a predicate, then $P(n)$ is either true or false, depending on the value of $n$. On the other hand, if $p$ is an ordinary function, like $n^2\ +\ 1$, then $p(n)$ is a numerical quantity. **Don’t confuse these two!**

### The Axiomatic Method

The standard procedure for establishing truth in mathematics was invented by Euclid, around 300BC [wikipedia reference](https://en.wikipedia.org/wiki/Axiomatic_system#History) 

Simply put his idea was to begin with 5 _assumptions_ about geometry, which seemed undeniable based on direct experience. Propositions like these that are simply accepted as true are known as _axioms_.

***Definition***: An _axiom_ is a proposition that is simply accepted as true based on direct experience.

Using said axioms, euclid established "proofs".

***Definition***: (As you've already read in the [[Introduction]]) A _proof_ is a sequence of logical deductions from axioms and previously proved statements that concludes with the proposition in question.

If I try and explain this, proofs are a way of "checking" the "trueness" of some statement. If you can conclude with the proposition in question, you've essentially proved the logical correctness of a statement. This allows the so called proof (if correct) to be unquestioned since it has a base in logical reasoning.

There are a few key terms that need to be established before proceeding:

- Important true propositions are called _theorems_.
- A _lemma_ is a preliminary proposition useful for proving later propositions.
- A _corollary_ is a proposition that follows in just a few logical steps from a theorem.

There's also some very important information regarding this:

> Euclid’s axiom-and-proof approach, now called the axiomatic method, remains the foundation for mathematics today. In fact, just a handful of axioms, called the Zermelo-Fraenkel with Choice axioms (ZFC), together with a few logical deduction rules, appear to be sufficient to derive essentially all of mathematics.

The ZFC axioms are important in studying and justifying the foundations of mathematics, but for practical purposes, they are much too primitive. By one reckoning, a formal proof in ZFC that 2 + 2 = 4 requires more than 20,000 steps!

It's better to assume a huge set of axioms. A good general guideline is simply to be up front about what you’re assuming.

##### Logical Deductions

Logical Deductions, or _inference rules_, are used to prove new propositions using previously proved ones. 

A fundamental inference rule is _modus ponens_. This rule says that a proof of $P$ together with a proof that $P\ implies\ Q$ is a proof of $Q$.

Inference rules are sometimes written in a funny notation. For example _modus ponens_ is written:

![modus ponens example](assets/modus-ponens-written.png)

When the statements above the line, called the _antecedents_, are proved, then we can consider the statement below the line, called the _conclusion_ or _consequent_, to also be proved.

> **Fun fact**: The term `modus ponens` literally means "_mood that affirms_" if translated from latin directly.

The key requirement of an inference rule is that it must be _sound_, i.e. whatever the antecedent, if it is true, it should also make the consequent true.

Here are some more inferences to go by:

```
	  P IMPLIES Q, Q IMPLIES R        
	-----------------------------     
	        P IMPLIES R
```

```
        NOT(P) IMPLIES NOT(Q)           
    ----------------------------
            Q IMPLIES P
```

As with axioms, we will not be too formal about the set of legal inference rules. Each step in a proof should be clear and _logical_; in particular, you should state what previously proved facts are used to derive each new conclusion.

### Proving an Implication

Propositions of the form: `If P, then Q` are called _implications_. This particular implication is often rephrased as: _"P implies Q"_. 

There are a few standard methods to prove such an implication. Let's have a look at them:

#### Method 1

Algorithm: 

1. Write _"Assume P"_.
2. Show that $Q$ logically follows.

There's a bit of advice about these in the book, which is very helpful:

> You’ll often need to do some scratchwork while you’re trying to figure out the logical steps of a proof. Your scratchwork can be as disorganized as you like—full of dead-ends, strange diagrams, obscene words, whatever. But **keep your scratchwork separate from your final proof, which should be clear and concise.**

Yet another important point to note is that proofs typically begin with the word: "Proof" and end with some sort of limiter, like $\blacksquare$  , which is known as QED. The only purpose for these conventions is to clarify where proofs begin and end. 

On a personal note:
> It helps to think of these proofs as stories. Each of these stories must have definite beginnings and endings, no "to be continue"s.


#### Method 2 - Prove the Contrapositive

***Definition***: An implication `"P IMPLIES Q"` is logically equivalent to it's _contrapositive_ $NOT(Q)\ \ IMPLIES\ \ NOT(P)$. 

To prove an implication by contrapositive, we use the following algorithm:

1. Assume $NOT(P)$ or $P'$
2. Prove: $Q'\ \implies\ P'$  by using [[Proofs#Method 1|Method 1]]. 

A common and popular example of using this method is shown in the following theorem:

***Theorem***: If $r$ is irrational, then $\sqrt r$  is also irrational.

A number is _rational_ when it equals a quotient of integers, i.e. if it can be represented in the form: $p/q$ where $q\ \neq\ 0$ . Thus, we must show that if $r$ is _not_ a ratio of integers, then $\sqrt r$  is also _not_ a ratio of integers. 

However, this is quite confusing. We can make it simpler using the contrapositive method instead:

_Proof_: We prove the contrapositive: if $\sqrt r$ is rational then, $r$ is rational.
Assuming that $\sqrt r$ is rational, there exist integers $p$ and $q$ such that:

$$\sqrt r\ = \frac{m}{n}$$
Squaring both sides, we get:

$$r\ =\ \frac{m^2}{n^2}$$
Since $m^2$ and $n^2$ are integers, $r$ is also rational. $\blacksquare$

### Proving an _If and Only If_

The phrase: "if and only if" is often abbreviated as: _"iff"_. Usually, it is used when there is a need to show a 2-way implication between 2 statements. For example: 

$$x +  y = 3 \iff x = 3 - y$$
Here's how we prove an "iff":

#### Method 1: Prove Each Statement Implies the Other

The statement $P \implies Q$ is equivalent to the two statements "$P \implies Q$ AND $Q \implies P$". So if we can prove $P\ \ iff\ \ Q$ by proving the two implications mentioned before. Here's the Algorithm to do so:

1. Write _"We Prove $P \implies Q$ and vice-versa"_.
2. Prove $P \implies Q$ using one of the methods for proving an implication.
3. Prove $Q \implies P$ using one of the methods for proving an implication.

#### Method 2: Construct a Chain of Iffs

In order to prove that $P \iff Q$:
1. Write, _"We construct a chain of iff implications"_.
2. Prove $P$ is equivalent to a second statement which is equivalent to a third statement and so forth until you reach $Q$.

##### Example

The _standard deviation_ of a sequence of values $x_{1}, x_{2}, x_{3}, ...,x_{n}$ is defined to be:
$$ \sqrt{ \frac{(x_{1}- \mu)^{2} \ + (x_{2}- \mu)^{2}\ + ... + (x_{n} - \mu )^{2}}{n} } = 0$$


