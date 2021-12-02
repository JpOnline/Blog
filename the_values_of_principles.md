# The value of ~~values~~ principles

Rules are very comfortable; they allow you to identify a pattern and then apply the steps described in the rule. You can not apply the same rule for every context, there are exceptions, but exceptions shouldn't hurt the principles behind the rules. Here's a little story to identify the difference between principles and rules.

Two students go to college and start to share a place. They talk:
 - Hey, what I could do that would bother you?
 - I'm here to study, noise bothers me, so be quiet
 - But I can't stay quiet the whole time. 
 - Cool, so be silent from 14h to 18h, it's good enough.

**Goal**: Learning.

**Principle**: Silence.

**Rule**: from 14h to 18h.

---

Another concept showed in this story is **goal**, and in Software Development a goal could be something like readability, portability, robustness, security, or even just working code that solves the intended problem. Very often we remember of rules and state that writing code in a certain way is better than another, forgetting the goals and principles driving that rules. 

Martin Fowler in his book [Refactoring](https://play.google.com/store/books/details?id=HmrDHwgkbPsC) defines refactoring as "a change made to the internal structure of software to make it easier to understand and cheaper to modify without changing its observable behavior." This definition is already stating that the resulting code should be easier to understand and cheaper to modify, but what if the final goal we are seeking is a higher modularity or more performance. In his book he gives a lot of examples of refactorings, and this is a great example of rules, but applying rules to your codebase without understanding why you are applying them might be making you further away from your goal. And what is interesting to analyze is that sometimes it gives examples about how to get from A -> B and also B -> A, so Fowler leaves for the reader to decide what is better.

In the decade of 1990 two famous people, one from MIT and another from Berkeley (but working on Unix) once met to discuss operating system issues. The person from MIT was interested in how Unix solved the PC loser-ing problem, that it's basically about how system calls that do long operations handle interrupts they cannot hold or mask. The MIT guy did not see any code that handled this case and asked the New Jersey guy how the problem was handled. The New Jersey guy said that the Unix folks were aware of the problem, but the solution was for the system routine to always finish, but sometimes an error code would be returned that signaled that the system routine had failed to complete its action. A correct user program, then, had to check the error code to determine whether to simply try the system routine again. The MIT guy did not like this solution because it was not the “right” thing. The New Jersey guy said that the Unix solution was right because the design philosophy of Unix was simplicity and that the right thing was too complex. Besides, programmers could easily insert this extra test and loop. The MIT guy pointed out that the implementation was simple but the interface to the functionality was complex. The New Jersey guy said that the right tradeoff has been selected in Unix -- namely, implementation simplicity was more important than interface simplicity. You can see more about this story in [Gabriel's](https://dreamsongs.com/RiseOfWorseIsBetter.html) and [Raymond's](http://catb.org/~esr/writings/taoup/html/ch13s01.html) texts.

A great example of principles to take a look is in [The Art of Unix Programming](http://catb.org/~esr/writings/taoup/html) (they name them rules, but they're actually principles), like the Principle of Optimization: prototype before polishing, and the Principle of Composition: design programs to be connected with other programs. [SOLID](https://en.wikipedia.org/wiki/SOLID) is also a good example of principles (at least the SOD part), and for tests I like [BDD (behavior-driven development)](https://en.wikipedia.org/wiki/Behavior-driven_development). BDD is usually described as a rule, to write tests in the form of GIVEN, WHEN, THEN. But from this rule we can extract the principle of writing tests as Finite State Machines, ie. make clear the initial state of the test, the action transitioning one state to another, and the expected state after this action.

Also take the classic [Design Patterns](https://play.google.com/store/books/details/Erich_Gamma_Design_Patterns?id=6oHuKQe3TjQC) for example, they are good rules for what to do when you see a code outlining a certain.. pattern. But we also have good examples of [how to apply the Design Patterns with simple functions](http://mishadoff.com/blog/clojure-design-patterns), so the question is, what's the goal to use the Design Pattern? What do we want to accomplish with it? Is it a more readable code, or a better generalization? If we reach the same goal using just functions and the solution is simpler, why would we not do that? You could be restricted by the programming language, but it's possible to work with high order functions in Object Oriented languages nowadays. In languages like Clojure, that are mainly known to be functional, you can choose to follow a stateful or Object Oriented style as well, so it's up to the developer and the team to assess the context and their principles to decide what to use in each situation.

There are a lot of principles and even more rules, so how to choose principles to prioritize? Well, the whole idea is to not have a rule that fits all cases, so is up to the team of developers with other stakeholders to decide what are their goals and what principles they will prioritize. If someone is saying that some code pattern or rule is right and another is wrong, be careful about it, you need to start with "why" and think about what are your principles, what is important to you, and what principles surrounds this rule. Then you are better suited to asses it and think if you can use that to solve your problem.