## I now declare it is opened the documentation week.
**The goal is to have a prototype by the end of the week**

I can see several problems related to that, when I get to work in big projects that exists for a long time, I usually 
spend a lot of energy to understand what is happening, what are the main elements, the domain entities. It might be because documentation gets unsynced with the code, but could be something else and what I'm going to do is to address this problem and produce a prototype by the end of the week. So if you have time, interest and energy, please contribute with insights. Thank you.

When you think about it, you see that documentation is already a solution of a problem, the problem of understanding a code that you are starting to work with.

## Nice to meet you
My name is João Paulo, I love to code and create real solutions for real problems. I love the Clojure programming language and I'm using it for about 2 years to create Progressive Web Apps using Web Components as a Free Lancer.

## The process
I'll address the problem of **documentation in software** for 5 days, each day with a very important role.

1. Map the problem
2. Sketch solutions
3. Decide the solution to prototype
4. Prototype
5. Test

## The Map (so far)
New Developer in unknown code\
-----⬇️-----\
**Extract relationships between chunks of code** 👀\
-----⬇️-----\
**See a rich visualization of the\
documentation that is in the code** 👀\
-----⬇️-----\
Edit the documentation\
-----⬇️-----\
Push changes with Git
 
I decided to focus in **Extract Relationships** and **Rich Visualization**. 

# Day 1
## Goal
- A tool that developers can run in a code base to **extract knowledge** or **facilitate code documentation**.
- Have 100 people answering 100% for the question: "What's the probability for you to recommend this tool for a friend or coworker?" The number is arbitrary but it's basically to find a niche with the [Net Promoter Score (NPS)](https://www.lightercapital.com/blog/net-promoter-score-how-to-calculate-nps/)

## Questions
- Diagrams are important for documentation?
- Describe important terms used in code to define a Ubiquitous Language (in DDD style) is desirable?
- Would be a good strategy to write code documentation near the code it’s related to so it would be versioned by git?
- Is it interesting to create a label system for chunks of code? So we could filter to visualize specific chunks at times, e.g. to see tests with the code it tests, to join the html with the css that it affects, to see code grouped by functionality when convenient, etc.
- The reason it’s hard to see an up to date documentation is because it’s far from the code?
- What are the actual problems with tools for documentation? I have some experience with javadocs and I like the fact that it is done with the code and you can see it in a web page, but it’s not possible to edit from there and it focuses on too technical detail about a single piece of code, not how they are related. I also think it’s interesting the [Visual Studio Code Maps](https://docs.microsoft.com/en-us/visualstudio/modeling/map-dependencies-across-your-solutions?view=vs-2019) and [C4 with Structurizr](https://youtu.be/HmHOYkTVxIg?t=1411)

## HMW statements
After some research and discussion with specialists I made some "How might we" statements, that's basically problems seen in an opportunity point of view.
- How might we improve the code knowledge of someone new in the team?
- How might we highlight the domain entities?
- How might we improve visibility of the code? (more than just coloring differently)
- HMW identify entry points?
- HMW sync the visualization diagrams and the code?
- How might we generate diagrams from the code?
- How might we show diagrams with too much elements?
- HMW curate automatic generated diagrams?
- How might we write documentation related to multiple chunks of code (hight level documentation)?
- HMW have nontrivial examples? (not only about units, but about the integration of them)
- HMW crete intermediare description? (not only about units, but about the integration of them)
- How might we make it easy to edit?
- HMW quickly jump between the code, the documentation, the tests, the examples?
- How might we improve searching?
- How might we facilitate collaboration?

[Comments and insights here](https://github.com/JpOnline/Blog/issues/9)
