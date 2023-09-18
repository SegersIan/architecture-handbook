## The Archtecture Handbook
Written and compiled by Ian Segers as personal guide for his job as Solution Architect.
In case you are reading this directyly on [GitHub](https://github.com/SegersIan/architecture-handbook), you can read this Markdown rendered on the [GitHub Page](https://segersian.github.io/architecture-handbook/).

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

> Refers to the **architectural style(s)** the system is implemented in. 
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
1. Make architecture decisions
    * Designs and design principles must **guide technology decisions** not dictate them.
    * You can instruct to use "reactive-based framework for web development" but not which one.
2. Continually analyze the architecture
    * Analyze the current architecture and technology environment and recommend solutions for improvement.
    * "How viable is the artchitecture from a few years ago, today? Given the changes in both business and technology"
    * This includes test/release environments, which allows for agility. Remind DevOps principles and practices.
3. Keep current with latest technology and industry trends
4. Actively ensure compliance with decisions
5. Technical breadth over technical depth.
    * Seek aggresively experience or exposure to multiple languages, platforms, and technologies.
6. Have business domain knowledge
    * Important for good communication, you do need to align with business needs.
7. Possess interpersonal skills
    * Teamwork, facilitation, and leadership.
8. Understand and navigate politics
    * Must understand the political climate and be able to navigate the politics,

Note that (7) and (8) are cruccial for the ability of the architect to have effective impact and to execute change.

### What is Enterprise Architecture?

...todo

## Usefull

* [Thought Leaders](thought-leaders.md)
* [Resources](resources.md)

## Copyright

This handbook is based on existing materials that I have read, combined with my own experience. Due to this, some text here can be close to the words of any of the materials I've read. For that reason I do my best to be transparent and share the relevant [resources](resources.md). I don't take credit for any of the wisdom to be found here.