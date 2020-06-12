## I now declare it is opened the documentation week.
**The goal is to have a prototype by the end of the week**

I can see several problems related to that, when I get to work in big projects that exists for a long time, I usually 
spend a lot of energy to understand what is happening, what are the main elements, the domain entities. It might be because documentation gets unsynced with the code, but could be something else and what I'm going to do is to address this problem and produce a prototype by the end of the week. So if you have time, interest and energy, please contribute with insights. Thank you.

When you think about it, you see that documentation is already a solution of a problem, the problem of understanding a code that you are starting to work with.

The code are the **facts**.\
The comments are the **knowledge** imputed by **human**.\
The tool will show you an interpretation, a **point of view**, a way to see the combination of **fact** and **human input**.

> Neo: Do you always look at it encoded?\
> Cypher: You get used to it. I don’t even see the code. All I see is blonde, brunette, redhead.\
> -- Matrix

The problem I'm trying to mitigate is the difficulty of understanding pre-existing code, usually when you enter in a new team or just need to work in some part you are not used to. It might be inevitable spending more energy in these situations, but I thing the documentation plays a big role in how much energy you'll spend in the end.

The documentation is simply information other people let to you about the code, if this information is up to date and right, it will definitely help you.

There's a cost for maintaining documentation and if this cost is higher than the benefits you get from it, you will avoid wasting resources on it. So I'm trying to increase the value extracting some information automatically and decreasing the cost by making it clear what parts are out of date.

## Nice to meet you
My name is João Paulo, I love to code and create real solutions for real problems. I love the Clojure programming language and I'm using it for about 2 years to create Progressive Web Apps using Web Components as a Free Lancer.

## The process
I'll address the problem of **documentation in software** for 5 days, each day with a very important role.

1. Map the problem
2. Sketch solutions
3. Decide the solution to prototype and create a Story Board
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

## Features (so far)
The code is tightly coupled with execution, sometimes it's difficult or dangerous to change things. Think about how hard it would be for you to restructure how your directories are organized. The tool creates a label system independent of directories, so it's easy and harmless to rename and move things around.

- Using labels to define multiple level of documentation.
- Run a basic static analysis to identify the function and where are they called to generate a diagram where you can filter elements you want to show/hide.
- Run this analysis in any language.
- Warn dev about missing code referenced in doc, maybe it was deleted or it changed the name.
- Show usage examples of the code (tests) close to the code it tests.
- Glossary (like DDD ubiquitous language)

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
- How might we write documentation related to multiple chunks of code (high level documentation)?
- HMW have nontrivial examples? (not only about units, but about the integration of them)
- HMW crete intermediare description? (not only about units, but about the integration of them)
- How might we make it easy to edit?
- HMW quickly jump between the code, the documentation, the tests, the examples?
- How might we improve searching?
- How might we facilitate collaboration?
- How might we show which parts of the code is poor/well documented?
- HMW show test coverage?
- HMW show results of tests in the documentation?

# Day 2
## References

Labels like gmail are better than directories to structure information.
<div>
  <img src="/documentation_sprint-images/gmail-labels.png" width=580>
</div>
<br>
<br>

[Clojuredocs.org](https://clojuredocs.org/clojure.core/when-let) has docstring, code examples, references to other functions, and comments in a single page.
<div>
  <img src="/documentation_sprint-images/clojuredocs.png" width=640>
</div>
<br>
<br>

Javadocs use comments in code to generate a rich view of documentation.
<div>
  <img src="/documentation_sprint-images/javadocs.png" width=580>
</div>
<br>
<br>

Graphviz are used to show relationship between things.
<div>
  <img src="/documentation_sprint-images/graphviz.png" width=480>
</div>
<br>
<br>

Devtools is a good interface to edit text and show visual change in real time.
<div>
  <img src="/documentation_sprint-images/devtools.png" width=640>
</div>
<br>
<br>

C4 model organize diagrams in "zoom" levels.
<div>
  <img src="/documentation_sprint-images/c4-overview.png" width=500>
</div>
<br>
<br>

Tags in social media improve searchability.
<div>
  <img src="/documentation_sprint-images/social-media-hashtag.png" width=80>
</div>
<br>
<br>

Wiki rely on links between pages to connect concepts.
<div>
  <img src="/documentation_sprint-images/wikipedia.png" width=80>
</div>
<br>

[Jupyter notebooks](https://jupyter.org/) and [Devcards](https://github.com/bhauman/devcards) are example of interactive code.
<div>
  <img src="/documentation_sprint-images/jupyter-notebook.png">
</div>
<br>
<br>

## Solution Sketches
### Collapsable Diagrams
<div>
  <img src="/documentation_sprint-images/collapsable-diagrams-0.png">
</div>
<div>
  <img src="/documentation_sprint-images/collapsable-diagrams-1.png">
</div>
<div>
  <img src="/documentation_sprint-images/collapsable-diagrams-2.png">
</div>
<br>

### Links Everywhere
<div>
  <img src="/documentation_sprint-images/links-everywhere.png">
</div>
<br>

### Some maybe useful ideas

Documentation is synced with code.
<div>  
  <img src="/documentation_sprint-images/documention-is-synced-with-code.png" height=250>
</div>
<br>

Can be used with any language.
<div>
  <img src="/documentation_sprint-images/language-agnostic.png" height=300>
</div> 
<br>

A possible label organization.
<div>
  <img src="/documentation_sprint-images/possible_labels.png" height=300>
</div>
<br>

Referencing Labels.
<div>
  <img src="/documentation_sprint-images/referencing-labels.png" height=250>
</div>
<br>

Labels are defined in a configuration file.
<div>
  <img src="/documentation_sprint-images/in-looser-file.png" height=300>
</div>
<br>

Showing markdown collapsable docstring in code.
<div>
  <img src="/documentation_sprint-images/showing-rich-collapsable-docstring-on-code.png" width=350>
</div>
<br>

# Day 3
The methodology says I should create a story board, but with the sketches I have and the fact I'm doing it alone I decided to create a script of what will happen in the prototype


- Dev is transfered to a new project by the boss.
  - Boss: I will put you to work in that project that was written 10 years ago, nobody knows how it works, a new bug appears when someone touches it. Also document what you learn while you work on it so it will be easy for the next.
  - Me: I've got it boss 👍🏼
- Dev search for "Documentation Tool" on Google.
- Dev finds Looset and get it from npm (or maybe some other package manager..).
- Dev runs it in his project "looset draw-map-shape/", it will start a server and serve the page in localhost:5667.
- * Dev opens the page and see the Main panel with a diagram, the label panel and the properties panel.
- Add new labels by edditing the labels properties of Code Blocks (CB) (it's going to appear a "+ create Main Api label" similar to tags in Google Keep)
- Hide CBs diagrams with no labels
- * Select a CB and click in the Page tab
- Fill the properties **examples**, **docstring** and **see-also**
- Click in the example link to go to its page (TODO: explain that the example properties is automatically synced in both CBs but not see-also)
- Deselect CB then the main panel will get back to white (empty).
- * Click in the Code tab (the main panel is still white) choose a CB that's shown with its docstring (with a option to collapse).
- Click in the Main Api label to show all CBs of that label.
- Click in the reset button to deselect all CBs and get back to the empty white view.
- * Click in Glossary tab (I'll think about this part later)
- Run `git pull` from the terminal (a test was deleted) and see that the page is updated with a warning (!) where that code was referenced.
- Put a label inside another label and fill **docstring** and **see-also** (html?)
- Dev checks `git diff` in terminal, `commit` and `push` the changes.

# Day 4
You can verify that I'm not following exactly one day after another, unfortunately I have to split my attentions to other projects. But I'll update it with the prototype soon.

<br>
[Comments and insights here](https://github.com/JpOnline/Blog/issues/9)
