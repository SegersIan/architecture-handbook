# Modularity    

Different platforms offer different reuse mechanisms for code, but all support some way of grouping related code together in *modules*. This concept of *modules* is proven slippery to define. Therefore, we will use a definition from the [Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/) | Chapter 3 book. 

Modularity is an organizing principle. IF an architect designs a system without paying attention to how the pieces wire together, a myriad of difficulties might be presented. Good modularity exemplifies the definition of an implicit architectural characteristic. No project features a requirement that asks the architect to ensure good modular distinction and communication, yet sustainable code bases require order and consistency.

## Definition

Modularity describes a logical grouping of related code, which could be a group of classes in a OO language or functions in a functional language. This grouping does't imply a physical separation, merely a logical one. 

When it comes to restructuring the architecture, the coupling encouraged by louse partitioning becomes an impediment to breaking the monolith apart. Thus, it is useful to talk about modularity as a concept separate from the physical separation forced or implied by a particular platform. **Components** *are the physical manifestation of modules*.

## Measuring

Given its importance, there are a variety of language-agnostic metrics to help measure modularity. There are 3 key concepts: *cohesion, coupling, and connascence*.

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

### Connascence



## Resources

* [Clean Architecture](https://www.amazon.com/dp/0134494164)
* [Fundamentals of Software Architecture | Chapter 3](https://fundamentalsofsoftwarearchitecture.com/)
