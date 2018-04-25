# Growing Software, The Metaphor Change

I know, reading an article of 16 pages is so boring. So here are some good extraction I got from one of those and also a following up paper. I brought what I think is the main point of the article and quickly pass by some other good points it makes.

## The Main Point

We've used the wrong metaphor since a long time ago and it was the article No Silver Bullet of Frederick Brooks that opened my mind. In the article he states that the word "building" is not precise, we should be using "growing" instead, and the related terms: specifications, assembly of components, scaffolding and architecture should be replaced for something else.

The article was written more than 30 years ago and it was already saying what we've heard in so many different ways later. At the time it was already advocating for rapid prototyping for requirements refinements, The prototype should implement what's important for the client because you don't know exactly what he wants and not even him, so spending time with the security or input verifications can be a waste if you are writing the wrong thing. This idea conciliates very well with the cycles we have in Scrum for example and the goal to fail fast. A big problem we have is the image that the software is a building. And like a building it is architected in advance, the cost is estimated, and the work is done when is built. The software is a living thing and it must evolve and adapt over time, even its architecture.

The building metaphor has a good image in our minds, and the misfortune of the article is not replacing this image with something else; so let's do it now, shaw we?  What else in the real world is grown instead of built? "Let  us  turn  to  nature  and  study  complexity  in  living  things, instead  of  just  the  dead  works  of  man", so let's say a tree, it's kind of a good metaphor but not very much, it has a really slow growth and it doesn't do very much, what I think is a good metaphor is a child, it's a more complex image and it needs to be taught, if you let it grow without attention it can become evil, unrefacterable and can collapse. We don't have an architect anymore we have a father or a mother. The architecture is about the constraints of the software, what it can access and where, the boundaries, and an architect is a person that create this restrictions for a static building, but the parents of a child are always providing the values that will guide the rest of the child's life, it's like giving a moral code for the software. The programmers are not bricklayers anymore, they are teachers, who are always teaching little new tricks, that of course, don't contradict the moral previously created.

I might agree that the family metaphor can be a bit awkward, so help me out here, what are we growing?

## Other Points

The article brings some other very good points that I would like to discuss more, but I'll pass by them very briefly for now. It splits complexity in Essential and Accidental, the first relates to the problem itself and the second to the implementation. It expose the difficulty of representing software graphically, it doesn't have a natural graphical representation as a map does for space. Also states how not creating the software yourself can be a good attack to the complexity and buying it as an option.

Ten years later the "No Silver Bullet Refired" continues the discussion very well talking about software reuse as another option for not creating it yourself and how costly it can be. Math functions are: 1. very costly to build yourself; and 2. very well defined and documented world wide. In a quote of Ivan Selin, Chairman of American Management Systems Inc., it states that "it is the [end] users, not the software people, who are reluctant to use packages because they think they will lose essential features or functions, and hence the prospect of easy customization
is a big selling point to them."

There are other two other very good quotes from the article.
The first is from James Coggins in the C++ Report:
> The problem is that programmers in O-O have been experimenting in incestuous applications and aiming low in abstraction, instead of high. For example, they have been building classes such as linked-list or set instead of classes such as user-interface or radiation beam or finite-element model. Unfortunately the selfsame strong type-checking in C++ that helps programmers to avoid errors also makes it hard to build big things out of little ones.

The second is from David Parnas
> The answer is simple. It is because [O-O] has been tied to a variety of complex languages. Instead of teaching people that O-O is a type of design, and giving them design principles, people have taught that O-O is the use of a particular tool. We can write good or bad programs with any tool. Unless we teach people how to design, the languages matter very little. The result is that people do bad designs with these languages and get very little value from them. If the value is small, it won't catch on.

Bibliography References:
- "No Silver BulletEssence and Accident in Software Engineering" by Frederick P. Brooks
- "'No Silver Bullet' Refired" by Frederick P. Brooks
