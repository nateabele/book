# Design-First Software

_By Nate Abele_

***

#### What do we mean when we talk about design?

_"Design is the rendering of intent." — Jared M. Spool_

When we talk about software design, we don't talk about the pixels that appear on the screen, but of the system behind the pixels, that brings them into being: how data flows through it, and how its components fit together.

...

## Axioms

Axioms are fundamental, self-evident truths. These truths will serve as the bedrock on which we can build a philosophy of, and approach to, software design.

Software design is about optimizing for two _dramatically_ different audiences, with complementary capabilities but diametrically opposing interests: computers and brains — specifically, human brains. What follows are the capabilities of each of the two audiences: what each is good at (and, conversely, what the other is terrible at).

### Brains
 - Ambiguity
 - Inference
 - Intuition

### Computers
 - Complexity
 - Lots of data
 - Dynamism — many things changing at once, continuously
 - Precision
 - Repetition


...

[Main book part goes here-ish...]

...

## But can't we just write tests?



### When dealing with state and side effects

Simple, well-defined units with clean boundaries are easy to reason about _independently_, but combine even a few of these units, and the number of possible interactions between them quickly grows by orders of magnitude (see also: [the halting problem](http://www.cgl.uwaterloo.ca/csk/halt/)). **@TODO**: _Find a reference that better explains the combinatorially-explosive growth of possible machine states relative to a linear increase in program size, and how it relates to the halting problem._

[Unknown unknowns](https://en.wikipedia.org/wiki/There_are_known_knowns) — Unexpected failure modes are, by definition, unexpected. We can only write tests for failure we can anticipate.

Integration complexity: one service invokes another using a callback that invokes a third, which, due to an unanticipated set of conditions, unexpectedly re-invokes the first, resulting in indirect mutual recursion.

### Instead of a type system

From the prior two points (unexpected failures & integration complexity), we can correctly infer that it is unreasonable to expect that (a) all units will always be called with expected values, or (b) that all units will correctly handle (_and_ be test-covered for) all values that will be passed to it in production.

### The state of the art: necessary, but insufficient

Even in a strongly-typed, pure functional language, automated testing only provides a few programmer-predicted snapshots of behavior within a universe of possible outcomes. Long-term, the only real solution for guaranteed software reliability is something like [total functional programming](http://www.jucs.org/jucs_10_7/total_functional_programming/jucs_10_07_0751_0768_turner.pdf), or other sub-Turing-complexity techniques that facilitate verification analogous to mathematical proofs; see also: [Epigram](http://cs.ru.nl/~freek/courses/tt-2010/tvftl/epigram-notes.pdf), [Coq](https://coq.inria.fr/a-short-introduction-to-coq).

## Resources

An aggregated collection of resources which may or may not be referenced in the book itself.

### Front-end
 - [React Stateless Functional Components: Nine Wins You Might Have Overlooked](https://hackernoon.com/react-stateless-functional-components-nine-wins-you-might-have-overlooked-997b0d933dbc)
 - [Machine-checked explicit state: An arrow in the heart of complex web applications](https://blog.reifyworks.com/machine-checked-explicit-state-an-arrow-in-the-heart-of-complex-web-applications-bbe1ef2038ed)

### Concepts

 - [The Mostly Adequate Guide to Functional Programming](https://drboolean.gitbooks.io/mostly-adequate-guide/content/) — Dr. Boolean (aka Brian Lonsdorf)
 - [Making Impossible States Impossible](https://www.youtube.com/watch?v=IcgmSRJHu_8) — Richard Feldman
 - [_Beyond_ series](http://blog.ircmaxell.com/search/label/Beyond) — Anthony Ferrara
 - [_Boundaries_](https://www.destroyallsoftware.com/talks/boundaries) — Gary Bernhardt
 - [The Clean Architecture](https://8thlight.com/blog/uncle-bob/2012/08/13/the-clean-architecture.html) — Uncle Bob


### Abstractions

 - [Promises](https://developers.google.com/web/fundamentals/getting-started/primers/promises)
 - [You're Missing the Point of Promises](https://blog.domenic.me/youre-missing-the-point-of-promises/)

### Theory

 - [_The Mythical Man Month_](https://www.amazon.com/Mythical-Man-Month-Software-Engineering-Anniversary/dp/0201835959) — Fred Brooks
 - [_The Design of Design_](https://www.amazon.com/Design-Essays-Computer-Scientist/dp/0201362988) — Fred Brooks
 - [Simple Made Easy](https://www.infoq.com/presentations/Simple-Made-Easy) — Rich Hickey
 - [Media for Thinking the Unthinkable](http://worrydream.com/MediaForThinkingTheUnthinkable/) — Bret Victor
 - [The Future Doesn't Have to Be Incremental](https://www.youtube.com/watch?v=gTAghAJcO1o) — Alan Kay

## Quotes

> “Extracting patterns from today's programming practices ennobles them in a way they don't deserve.” — _Alan Kay_
 
