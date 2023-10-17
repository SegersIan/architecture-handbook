# Modularity    

Different platforms offer different reuse mechanisms for code, but all support some way of grouping related code together in *modules*. This concept of *modules* is proven slippery to define. Therefore, we will use a definition from the [Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/) | Chapter 3 book. 

Modularity is an organizing principle. IF an architect designs a system without paying attention to how the pieces wire together, a myriad of difficulties might be presented. Good modularity exemplifies the definition of an implicit architectural characteristic. No project features a requirement that asks the architect to ensure good modular distinction and communication, yet sustainable code bases require order and consistency.

## Definition

Modularity describes a logical grouping of related code, which could be a group of classes in a OO language or functions in a functional language. This grouping does't imply a physical separation, merely a logical one. 

When it comes to restructuring the architecture, the coupling encouraged by louse partitioning becomes an impediment to breaking the monolith apart. Thus, it is useful to talk about modularity as a concept separate from the physical separation forced or implied by a particular platform. **Components** *are the physical manifestation of modules*.

## Measuring

Given its importance, there are a variety of language-agnostic metrics to help measure modularity. There are 3 key concepts: *cohesion, coupling, and connascence*.

### NOTE!

> This measuring techniques come from the structured programming field. Some of it might also apply to OO and Functional paradigms, however, these metrics are originally targeting structured code bases.

### Cohesion

Refers to what extent the parts of a module should be contained within the same module. Measuring how relates parts are to each other. Ideally a cohesive module is one where all the parts should be packaged together. Attempting to divide a cohesive module would only result in increased coupling, and decreased readability.

* [Types of Cohesion](https://en.wikipedia.org/wiki/Cohesion_(computer_science)) - From best to worst:
    * *Functional Cohesion*
    * *Sequential Cohesion*
    * *Communication Cohesion*
    * *Procedural Cohesion*
    * *Temporal Cohesion*
    * *Logical Cohesion*
    * *Coincidental Cohesion*
* The [Chidamber and Kemerer Object-oriented metrics suite](https://en.wikipedia.org/wiki/Programming_complexity) are a well known set of metrics that allows to measure the "Lack of Cohesion", also known as the LCOM (Lack of Cohesion of Methods) formula. 
    * LCOM: The sum of sets ofg methods not shared via sharing fields.
    * Useful to analyze code base in order to move from one architectural style to another.
    * Only measures *structural* lack of cohesion; not to determine logically if particular pieces fit together. It tells us **HOW** but not **WHY**.

### Coupling

A basic measuring method would be by just measuring afferent and efferent coupling:
* *Afferent* Coupling: Incoming connections/dependencies to a code artifact. (ingress/incoming)
* *Efferent* Coupling: Outgoing connections/dependencies to a code artifact. (egress/outgoing)

The following approach allows for a deeper evaluation than the basic afferent/efferent measurements.

* **Abstractness**: The ratio of abstract artifacts (abstract classes, interfaces, ...) to concrete artifacts (implementation).
* **Instability**: The ratio of efferent coupling to the cum of both efferent and afferent coupling.
    * Determines the volatility of a code base. A code base that has high instability breaks more easily because of the high coupling. If a class calls to many other classes to delegate work, the calling class shows high sensitivity to breakage if one or more of the called methods change.
* **Distance from Main Sequence**: `Distance = | Abstractness + Instability - 1 |`
    * This is a derived metric from Abstractness and Instability.
    * This metric imagines an ideal relationship between abstractness and instability; classes that fall near this idealized line exhibit a health mixture of these two competing concepts.
    * [Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0303.png)
    * There are [2 zones](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0303.png) where a code artifact can fall
        * *Zone of uselessness*: Code that is too abstract becomes difficult to use.
        * *Zone of pain*: Code with too much implementation and not enough abstraction becomes brittle and hard to maintain.
 
### Connascence

A refinement of the afferent/efferent measures towards OO.

> Two components are connascence if a change in one would require the other to be modified in order to maintain the overall correctness of the system.

#### Static Connascence

Source-code-level coupling, the degree to which something is coupled, either afferent or efferent:

* *Connascence of Name (Con)*:
* *Connascence of Type (CoT)*:
* *Connascence of Meaning (CoM) or Connascence of Convention (CoC)*:
* *Connascence of Position (CoP)*:
* *Connascence of Algorithm (CoA)*:


#### Dynamic Connascence

## Resources

* [Clean Architecture](https://www.amazon.com/dp/0134494164)
* [Fundamentals of Software Architecture | Chapter 3](https://fundamentalsofsoftwarearchitecture.com/)
