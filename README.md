# The Archtecture Handbook

Written and compiled by Ian Segers as personal guide for his job as Solution Architect.
In case you are reading this directly on [GitHub](https://github.com/SegersIan/architecture-handbook), you can read this Markdown rendered on the [GitHub Page](https://segersian.github.io/architecture-handbook/).

This is a static website which gets easily cached. To make sure to have the latests contents, do a hard refresh (CTRL + SHIFT + R for windows).

## Systems

Before we dive into Software Architecture, we must talk about Systems.

For a System we can find a definition like:

> a set of things working together as parts of a mechanism or an interconnecting network; a complex whole.

Or more specifically for Software Systems:

> System software is a set of generalized programs that manage the resources of the computer, such as the central processing unit, communication links, and peripheral devices

However, as you will read further about *Evolutionary Architecture* you might understand why I personally like to keep the following definitio:

> a group of body organs that together perform one or more vital functions

Either way, a **System** is a concept, far more general than software/IT systems. There is a field of [Systems Thinking](https://en.wikipedia.org/wiki/Systems_thinking). If you want to read more about it, I suggest [Thinking in Systems: A Primer](https://en.wikipedia.org/wiki/Thinking_In_Systems:_A_Primer).

## Software Arhitecture

This section is based on [Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/).

### What is Software Architecture?

In software engineering we work with **(IT) systems**, so when we talk about the software architecture, we are talking about the **architecture of a system**, which can exist out out of many sub-systems, which on their own can exist out of many sub-systems and so on.

Software Architecture consists of:
1. The **structure** of the system (heavy grey lines).
2. The **desired characteristics** (-ilities) of the system.
3. The **architecture decisions**
4. The **design principles**

![Software Architecture Definition](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0102.png)

#### 1. Structure of the system

> Refers to the [**architectural style(s)**](architecture-styles.md) the system is implemented in. 
> When we talk about an micro-service architecture, we're talking about the structure of the system, not the architecture, cause the architecture also describes the characteristics, decisions, and design principles.

[Structure Of the System Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0103.png)

#### 2. Desired characteristics of the system

> Describes basically **how we want the system to behave**. See [the characteristics list](architecture-characteristics.md) for an detailed list of examples. The *desired* behaviour and other charactericis vary widely per system.

[Characteristics Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0104.png)

#### 3. Architecture Decisions

>Describes the **rules** for how a system should be constructed. These form the **constraints of the system** and **informs the developers on what they can and cannot do**.
>Exceptions to these rules can happen, such a exception is also called a *variance*. Based on the size of an organization, an Architecture Decision Board (ADB) or an indivdual architect can grant such exceptions. This is very common, as there are always exceptions to the rule. An exception is usually only for a given part of the system. It doesn not hurt to measure the amount of exceptions that are granted.

Example: The presentation layer is not allowed to call the database layer directly.

[Architecture Decisions Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0105.png)

#### 4. Design Principles

>Describes the **guidelines** for how a system should be constructed. Instead of a hard rule, like the architecture decisions, the guideliness are intended to "guide".

Example: "Wherever possible, leverage async communication for decoupling"

[Design Principles Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0106.png)

### What is a Software Architect?

*There is much to be said about this, the scope and responsibilities of an Software Architect has evolved and continues to expand. Initially the role was very technical, in todays world we have roles like Technical, Solution and Enterprise architects.*

*Architectural wisdom and ideas can very specific for their time they were documented. As technology constantly changes, many aspects regarding architecture will change along with that.*

*An example would be the introduction of tools like Kubernetes, which made the restructuring of any software topology cheap, which allows for a more evolving topology. A decade ago, such decisions were costly, so mostly final, once they were made.*

The role has the following core expectations:
1. Make **architecture decisions**
    * Designs and design principles must **guide technology decisions** not dictate them.
    * You can instruct to use "reactive-based framework for web development" but not which one.
2. Continually **analyze the architecture**
    * Analyze the current architecture and technology environment and recommend solutions for improvement.
    * "How viable is the artchitecture from a few years ago, today? Given the changes in both business and technology"
    * This includes test/release environments, which allows for agility. Remind DevOps principles and practices.
3. **Keep current with latest** technology and industry **trends**
4. Actively **ensure compliance** with decisions
5. **Technical breadth over technical depth**
    * Seek aggresively experience or exposure to multiple languages, platforms, and technologies.
6. Have **business domain knowledge**
    * Important for good communication, you do need to align with business needs.
7. Possess **interpersonal skills**
    * Teamwork, facilitation, and leadership.
8. Understand and **navigate politics**
    * Must understand the political climate and be able to navigate the politics.

In addition to these core expectations, there are many more and this will change as technology and scale changes.

Note that (7) and (8) are cruccial for the ability of the architect to have effective impact and to execute change.

### Evolutionary Architecture

That change is constant, is a fundamental fact for many areas of life. This is no different for software systems and software architecture. 

Architecture will have to evolve, if the systems wants to survive over a long time. A system is like a biological organism, it must adapt and change to survive. Survival of the fittest is a law that also exists for organisations and the systems that support them.

> Survival of the fittest... suggestes that organisms best adjusted to their environment are the most successful in surviving and reproducing.

In [Building Evolutionary Architectures](https://www.oreilly.com/library/view/building-evolutionary-architectures/9781491986356/) the authors build further on the concept of Evolutionary Architectures.

**As an architect, you should take this in consideration. Try to define your architecture in a way that allows and expect change over time. Business and its requirements change constantly, as the technologies and platforms that support them.**

### Understanding Needs

To do good architecture, one must really try to understand the **needs of all the stakeholders** involved, and **understand their priorities**. **All your architectural decisions should be guided by the this**.

## Usefull

* [Thought Leaders](thought-leaders.md)
* [Resources](resources.md)

## Copyright

This handbook is based on existing materials that I have read, combined with my own experience. Due to this, some text here can be close to the words of any of the materials I've read. For that reason I do my best to be transparent and share the relevant [resources](resources.md). I don't take credit for any of the wisdom to be found here.