# An Architecture for Community Contribution, Speed and Modularity
I'll tell you some of my opinions about Software Architecture and what are our plans for Looset.

It'll watch you source files changes to show in real time a dependencies diagram and Code Block viewer independent of the filesystem. Check it out on the [main page](https://jponline.github.io/looset-landing/).

We haven't started to work in Looset yet, but I've thought a bit about its architecture. I believe the "building" metaphor is bad when talking about software, I prefer the "grow" metaphor. When we think about our software as a living organism that needs constant care we make better decisions about it.

There are a lot of rules around how to create software, "you should use this design pattern", "you should write your tests first", TDD, "you should model according to your domain first", DDD, "behavior first", BDD, SOLID, Hexagonal (Onion) Architecture, Layers and Modules, etc. I value most of what I mentioned here, but I prefer to understand the principles they reflect. In this direction I like [The Art of Unix Programming](http://catb.org/~esr/writings/taoup/html/) and there's a summary of the principles stated there in [a wiki](https://en.wikipedia.org/wiki/Unix_philosophy#Eric_Raymond's_17_Unix_Rules).

I'm influenced by two other ideas: The first, I've heard from Martin Fowler, opposing the statement that "The architect is the responsible for making the big important initial decisions" he said something as ["The architect should let options open"](https://martinfowler.com/articles/oss-lockin.html). The second I got by reading [Clean Architecture](https://www.oreilly.com/library/view/clean-architecture-a/9780134494272/#toc) by Uncle Bob, where he points out that the farther a module is from the business rules, more this module should work as a plugin. I.e, frameworks and databases should work as plugins. And then I started to think what other decisions can I let open and structure as a plugin? Maybe an i18n system, maybe the programming language itself.

To see this project becoming reality you can contribute in the [Kickstarter Campaign](https://www.kickstarter.com/projects/looset-team/looset?ref=1i0fmm). We're asking what we need to be able to work on it, and it will be a Free Open Source Software.

I have some general goals when writing software:
- Extensibility: that the accretion of features don't become slow and dangerous to existent features when the projects grow big.
- Readability - Easy to read and understand.
- Maintainability, Flexibility or Testability - Decoupling in a way that if we change a module it won't break the system in different places.
- Robust - Handles well unexpected errors.

For Looset we have some more specific goals:
- Community contribution
- Speed
- Modularity

## Back-end
I've been working in Clojure for some time now and it has been a constant match between my personal development philosophy and its own and community philosophy. But I understand that other people might have other personal preferences or use a different stack that works better in specific domains.

For this reason we decided to write Looset modules as independent scripts programs that are called using bash. For instance we'll write a Basic Analyzer in Clojure using [babashka](https://github.com/borkdude/babashka), but we'll let it open for other language specific analyzers to be written in any script language. What could be seen as a sort of Micro Service architecture. One could decide to use Python to write an analyzer for C or even integrate a project as [Lezer](https://lezer.codemirror.net/).

In Clojure, most of the data are maps, it is part of the philosophy. As data will need to be shared across different languages and even the front end, it'd make sense to write it in Clojure EDN (Extensible Data Notation), but thinking in more general adoption we'll write the data as files in JSON, also being inspired on how Git works.

## Front-end
Most people would agree that making decisions about the Front-end is very different from making decisions about the back-end. But we still want to maximize the community contribution and modularity, still letting options open. So we decided to write Looset views as independent Web Components that will be used in a basic HTML page. For instance we'll write components using Clojurescript and [Reagent](https://reagent-project.github.io/), but we'll let it open for other languages and frameworks that support exporting as Web Components. One could decide to use Angular or Vue.js to write a new functionality.

I've already created a web app from scratch without a State Management System as Redux or [Re-Frame](http://day8.github.io/re-frame/) and I know how this is important. I would say that the most important is not the library but the idea, so the main point is to have the app state to be global, change it by firing events and subscribe components to the changes. I'm still investigating how we're going to use it in a way it's available to any web component in any framework.

Other decisions about how to structure the app state also needs to be done. I like to have it as normalized as possible and splitting what are domain entities (basically what we would write in a database) and UI models (component states) also computing as little as possible in the rendering phase, [treating the UI as a Finite State Machine](https://cognitect.com/blog/2017/5/22/restate-your-ui-using-state-machines-to-simplify-user-interface-development).

## Tests
I like the Test Driven Development approach, what is good not only for tests but for structuring dependencies in a testable way. I tend to write them in a BDD style using the [Given, When, Then Gherkin syntax](https://cucumber.io/docs/gherkin/reference/). We'll mostly write unit tests for the back-end, but I don't think unit tests are that valuable for the front-end. I've already used [Puppeteer](https://github.com/puppeteer/puppeteer) to write end-to-end tests, clicking in buttons, taking screenshots, etc. But for Looset we'll use it basically to have a production like environment, but only firing events and checking the result app state.

Another strategy that is sometimes viewed as tests, but I use more as a way to develop and prototype is [Devcards](https://github.com/bhauman/devcards). We'll use it to visualize all components in multiple states at once while we're developing and tweaking the app state.

## Speed
In most projects the performance is not a top priority for me because I don't expect to work with huge amounts of data, what's different in this project. A main concern is how fast it's going to be to interact with big projects generating large graphs. To address this problem we'll have Web Workers or background processes generating caches for the visualizations.

## Kickstarter
We created a campaign to both validate the interest and also to be able to invest the amount of time that this project requires. The campaign asks for a one time contribution of any amount and it's all or nothing, you'll be changed at the end of the month and only if we reach the goal.

[Looset main page](https://jponline.github.io/looset-landing)

[A video demo of the tools](https://youtu.be/x5mZcIVAPcg)

[The Kickstarter Campaign](https://www.kickstarter.com/projects/looset-team/looset?ref=1i0fmm)

<iframe src="https://www.kickstarter.com/projects/looset-team/looset/widget/card.html?v=2" width="430" height="510" frameborder="0" scrolling="no"></iframe>
