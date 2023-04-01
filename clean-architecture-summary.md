# clean-architecture-summary
This is my personal summary of the Clean Architecture book written by Uncle Bob

# Chapter 1: What is Design and Architecture

- `The goal of good software architecture is to minimize human resources required to build and maintain the required system.`

The signs of a mess (bad architecture) are when increasing the number of developers results in a small 
or non-existent growth of code and productivity. The end result is frustration: Executives have higher payrolls for marginal output in productivity and
developers work hard, but have to focus all their efforts into managing the mess to implement small features.

A comparisom to Aesops story of the `Tortoise and the Hare` is drawn. In which developers are in a constant race but exhibit overconfidence in the ability to remain productive: `We can clean it up later; We have to get to market first`. However, market pressure is relentless and continuous and there is no time to go back and clean things up. Developers who accept the lie that `Writing messy code makes a developer go faster in the short term` are experiencing the overconfidence of the hare. In the end: `Making messes is always slower than staying clean, no matter which time scale you are using`. To resolve decline in productivity, developers need to stop thinking like the hare and take responsibility of the mess they have made. 

Note: Often a proposed solution is to start over, this is a sign of overconfidence and will most often result in a similar to mess to the original project.

# Chapter 2: A Tale of Two Values

A software system provides two values to stakeholders. Developers often focus on the first but neglect the second.

- <b>Behavior</b>: Programmers are hired to make machines behave in a way to make / save money for the stakeholders. They believe their job is to implement requirements and fix bugs.

- <b>Architecture</b>: Stakeholders provide a stream of changes. The more the architecture prefers one shape over another, the more difficult these changes are to implement.

- `Eisenhower Matrix: I have two kinds of problems, the urgent and the important. The urgent are not important and the important are not urgent.`

The dilemna of software developers is that business managers cannot evaluate the importantance of architecture. It is the responsibility of the software team to assert the importantance of architectue over the urgency of features. As a developer you have a stake in the software and that is part of your role and what you were hired for. If the architecture comes last, the system will become more costly to develop over time. If this happens the software team did not fight hard enough.

# Chapter 3: Programming Paradignms

Each paradigm removes capabilities from the programmer. A paradigm tells us `what not to do` rather than `what to do`. All remove the `goto` statement.

- <b>Structured Programming:</b> Allows modules to be recursively decomposed into provable units, which in turn means that modules can be functionaly decomposed. Types of Proofs:
  -  Mathematical: Was never built as it is too laborous to prove every function correct 
  -  Scientific: Do not prove statements true, but rather prove statements false.
  -  Tests: Testing shows the presence, not the absence, of bugs

  Software is like a science. We show correctness by failing to prove incorrectness, despite our best efforts.

- <b>Object-Oriented Programming:</b> OO is the ability , through the use of polymorphism, to gain control over every source code depndency in the system. It allows an architect to create a plugin architecture  where high level policies are independent of low level details.

- <b>Functional Programming:</b> Immutability removes deadlocks and concurrent update issues. With enough processing power, applications can be entirely immutable and therefore `functional`.
  - Segregation of Immutabity: Segregate mutable from immutable components and try to push as much processing into the immutable components. 
  - Event sourcing is when we store transactions, but not the state. When state is required, all transactions are replayed. It required lots of memory to store all transactions and nothing gets deleted (CR) only.
