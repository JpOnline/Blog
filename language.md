# Language

Hey there, you might not want to read the whole text, you seem a pretty busy person to me, so I'll cut the chase, here is the conclusion and if you want to know more about how did I get there or the arguments behind it I invite you to read the following paragraphs.

You don't have an excuse to produce something complicated, if someone else is not understanding you it is because you're not explaining well enough. When developing a software you need to abstract down the complexity and make anyone that knows English and the domain of the software understand what is happening there, the reader doesn't need to know what is a `select`, `map`, `foreach` and not even `if..else` and languages like C# and Java don't help us to do it in a straight way.

## What is a language?
Language is the capacity to express an idea and communicate through a system of signs with a semantic and, most often a syntax common to a people who are of the same community or nation, the same geographical area, or the same cultural tradition. It's not static, new words and expressions are invented all the time.

It's possible for two people to say they speak the same language and not understand one another, here is an example of the situation: a more obvious example is a person close to hers 50 years old listening to a group of teenagers talking, they will probably have a lot of slangs in their vocabulary. Another example I want to give here is about context: imagine starting to read a scientific paper skipping the first 2 or 3 section and facing something like "with the injection of PPRS the VFD have decreased causing TPC in few days" even knowing about the subject of the paper it can have a lot of acronyms that was defined previously that's not of your knowledge.

I've talked so far about Natural Languages, are they different of Programming Languages (or Formal Languages)? Not really, what happens to Programming Languages is that the communication is with a computer and we communicate commands, not ideas.
But let's see some common characteristics of languages:

## Syntax and Semantic
The syntax is, originally , the linguistic branch that studies the way the words are combined to form phrases or announces.

We distinguish the syntax, that concerns the words of expressions, of the semantic, that concerns the means, the significations of expressions.

The semantics of a programming language is the meaning of the expressions, statements, and program units. For example, the syntax of a Java while statement is

```Java
while (boolean_expr) statement
```
The semantics of this statement form is that when the current value of the Boolean expression is true, the embedded statement is executed. Otherwise, control continues after the while construct. Then control implicitly returns to the Boolean expression to repeat the process.

Although they are often separated for discussion purposes, syntax and semantics are closely related. In a well-designed programming language, semantics should follow directly from syntax; that is, the appearance of a statement should strongly suggest what the statement is meant to accomplish. [Sebesta]

## Abstraction
I'll try to explain abstraction with a logic exercise, follow me please:
Take the sentence "It's raining in the city.", a simple definition of "rain" could be  "water falling from sky." and we could replace our first statement to "Water is falling from sky in the city.", we can do it again for "water" and we have "A transparent and tasteless liquid is falling from sky in the city.", last time "A transparent and tasteless liquid is falling from sky in a populated area with houses and buildings.". We could keep doing it until we have a very long sentence with fewer words repeated several times that (in some sense) is equivalent to the first sentence. This is called Top-bottom approach when we are developing software.

All we do when designing software is to manage complexity. And creating proper abstractions is the only way to decrease complexity by hiding irrelevant details.
The ultimate language that the computer "understands" is binary, but this one is too complex, it's hard to write and hard to read. We use languages different than binary for the benefit of human, so we can communicate among ourselves while the computer keeps understanding us. So if you are able to abstract your `if..else` to something it's easier to understand, why would you let it there?

## Domain Specific Language (DSL)
So far we understand that high level languages were created to have a human-to-human better communication, what if even though we're not understanding ourselves very well, take database managing for instance: a developer can choose hundreds of different ways to query and change data. One solution for this is SQL, a Domain Specific Language created to manage relational databases, so we have specific syntax and operators for dealing with databases, but do we need a new language? Could we extend our general purpose language to have all the benefits SQL bring us? To answer that I'll give 2 examples:
The first one is the LINQ, a C# .Net library that let you to write queries like

```csharp
users
    .where(user => user.column1 == "yes" &&
        user.column2.Contains("/string/"))
    .Count();
```
And Lisp macros, that allow you to create a library that understands something like [*](https://stackoverflow.com/a/268041/3646180)

``` closure
(sql select count(*)
    from users
    where column1 = "Yes"
    and column2 like "%string%")
```

The point is that we're capable of creating our own DSLs in our general purpose language and, in fact, we do it all the time; every time you create a new function or a new variable you are extending the language by adding verbs and nouns to it.

> Every system is built from a DSL designed by the programmers to describe that system. The art of programming is, and has always been, the art of language design. [Clean Code: Functions, Robert Martin]

If we are creating our own DSLs, what is left for general purpose languages? Well they need to help us in this job, they need to provide us tools to build abstractions and we create them to restrict the generality of the language. Some of the most used languages nowadays have several restrictions built-in, this is like asking a professional pilot to go slow, we're not children that can not handle the responsibility that comes with the power of general purpose languages, we can build our own restrictions when needed.

We already have all the power we need since a long time ago, we need to stop to expect languages and frameworks to save us and make things easier, we need to take the responsibility, extending the language, creating libraries and frameworks to handle the specific problems of our domain.

[What are your thoughts about it?](https://github.com/JpOnline/Blog/issues/3)

Bibliography References
- Wikipedia: Langage
- Wikipedia: Formal language
- Wikipedia: Syntaxe
- ANSI Common Lisp, Paul Graham
- Clean Code, Robert Martin
- Clean Architecture, Robert Martin
- Concepts of programming languages / Robert W. Sebesta.—10th ed.
- Code Complete2
