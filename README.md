## The Archtecture Handbook
Written and compiled by Ian Segers as personal guide for his job as Solution Architect.
In case you are reading this directyly on [GitHub](https://github.com/SegersIan/architecture-handbook), you can read this Markdown rendered on the [GitHub Page](https://segersian.github.io/architecture-handbook/).

## Software Arhitecture

### What is Software Architecture?

[Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/) suggest the following.

In software engineering we work with **(IT) systems**, so when we talk about the software architecture, we are talking about the **architecture of a system**, which can exist out out of many sub-systems, which on their own can exist out of many sub-systems and so on.

Software Architecture consists of:
1. The **structure** of the system (heavy grey lines).
2. The **desired characteristics** (-ilities) of the system.
3. The **architecture decisions**
4. The **design principles**

![Software Architecture Definition](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0102.png)

#### 1. Structure of the system

Refers to the **architectural style(s)** the system is implemented in. 
When we talk about an micro-service architecture, we're talking about the structure of the system, not the architecture, cause the architecture also describes the characteristics, decisions, and design principles.

* [Structure Of the System Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0103.png)

#### 2. Desired characteristics of the system

Describes basically **how we want the system to behave**. See [the characteristics list](architecture-characteristics.md) for an detailed list of examples. The *desired* behaviour and other charactericis vary widely per system.

* [Characteristics Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0104.png)

#### 3. Architecture Decisions

Describes the **rules** for how a system should be constructed. These form the **constraints of the system** and **informs the developers/engineers on what you can and can't do**.
Exceptions to these rules can happen, such a exception is also called a *variance*. It is commong\ in organizations that a Architecture Decision Board (ADB) or an equivalent authority is the entity that can grant exceptions. This is very common, as there are always exceptions to the rule. An exception is usually only for a given part of the system.

Example: The presentation layer is not allowed to call the database layer directly.

* [Architecture Decisions Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0105.png)

#### 4. Design Principles

Describes the **guidelines** for how a system should be constructed. Instead of a hard rule, like the architecture decisions, the guideliness are intended to "guide".

Example: "Wherever possible, leverage async communication for decoupling"

* [Design Principles Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0106.png)

### What is a Software Architect?

The industry itself doesn't have a good definition itself. However, Neal and Mark of [Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/) have tried to loosly explain this with a small [mind map](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0101.png) which is incomplete (their own words).

![mind map](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0101.png)

Note that the scope and responsibilities of an Software Architect has evolved and continues to expand. Initially the role was very technical, in todays world there are many layers of abstraction and lensens to look at a software architecture. This lead to roles like Technical, Solution and Enterprise architects.

Software engineering is not an exact science, so neither is the architecture part of it. Due to the changing nature of software engineering, we can expect this roles and definitions to evolve further to accomedate the changes in the industry. Therefore, many materials which are relevant today, can be outdated tomorrow. 

An example would be the introduction of tools like Kubernetes, which made the restructuring of any software topology cheap, which allows for a more evolving topology. A decade ago, such decisions were costly, so mostly final, once they were made.

#### My personal definition

*Taking the aforementioned thoughts in consideration, here is my "attempt" of a defintion which describes the contemporary situation.*

Software Architecture is harmonization of the system landscape between business and engineering. The idea is to make sure that the technical infrastructure, design, and implementation can accomedate business needs

The field is constantly changing, so is the defition of software architecture.

* [Who Needs an Architect](https://martinfowler.com/ieeeSoftware/whoNeedsArchitect.pdf)

### What is Enterprise Architecture?

...todo

## Usefull

* [Thought Leaders](thought-leaders.md)
* [Resources](resources.md)

## Copyright

This handbook is based on existing materials that I have read, combined with my own experience. Due to this, some text here can be close to the words of any of the materials I've read. For that reason I do my best to be transparent and share the relevant [resources](resources.md). I don't take credit for any of the wisdom to be found here.