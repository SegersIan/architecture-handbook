## Topics to cover - AKA THE TODO
* What is Software Enterprise Architecture
* How to get "TRUST" from the engineering team, and how to measure it (doing surveys for example)
* How to get architecture in the "AGILE" or "SAFE" ecosystem ?
* How to get architecture adapted all together
* Where/how does "clean Architecture" fit in ?
* Make a good split and difference between architecture and enterprise architecture
* Consider on how to discuss the points of Software Architecture and the hard parts book
* Consider how the architect elevator fits the big picture.
* Discuss managed evolution, but go deeper, what it solves or does. Like, IT allignment. Circle that back to the enterprise architecture and understand how the role of IT is perceived and the relation.
* Emphasize how 'data' and *'relations/connections* impact architecture.
* The concepts of "lenses/views" and how they can be used. Which are they, and when to use which ones?

* Look at managed evolution KPIs
* Make a throrough list of fitness function examples
* Domain Events, Event Driven Architecure, Even Sourcing...
    * https://martinfowler.com/articles/201701-event-driven.html
* "Emerging design/architecture"
* Add also something about all the database reading models, like eventual consistency and such. Cause this is very important when architecting or designing stuff, and the what you should take in consideration.
    * https://www.microsoft.com/en-us/research/wp-content/uploads/2011/10/ConsistencyAndBaseballReport.pdf
    * Also see the Data instensive applications
* Technology radar and application radar
* SAGA Pattern
    * Choreography (is basically event driven choreography, while orchestration is more SAGA as you would know it. I would do research if "SAGA Choreography" is really SAGA all together, read back the original whitepaper to validate.)
    * https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/saga/saga
    * Orchestration 
* Hexagonal Architecture

* ". I think that one of an architect’s most important tasks is to remove
architecture by finding ways to eliminate irreversibility in software designs." martin fowler

* "Software is not limited by physics, like
buildings are. It is limited by imagination, by design, by organization. In
short, it is limited by properties of people, not by properties of the world. “We
have met the enemy, and he is us.” - ralph johnson

* Architecture domains/domains/fields
    * Application Architecture
    * Integration Architecture
    * Infrastructure Architecture

## Architecture over time - patterns
Discuss patterns or techniques which allow to gradually migrate from todays architecture/design to the target architecture/design.

* Parallel Run
* Dark launching
* Feature toggles
* Strangler pattern
* Granualar roll out 
* Feedback channels
* ...

## Others

### Understanding Needs

To do good architecture, one must really try to understand the **needs of all the stakeholders** involved, and **understand their priorities**. **All your architectural decisions should be guided by the this**.

### Component Principles

### Component Chesion

*based on [Clean Architecture](https://www.amazon.com/dp/0134494164)*

### Component Coupling

*based on [Clean Architecture](https://www.amazon.com/dp/0134494164)*

### X is a Detail

*based on [Clean Architecture](https://www.amazon.com/dp/0134494164)*

- Add your thoughts on how this element is relevant in larger architectures, and about microservices , where if the service is small enough, it might be less "important". I think it's still relevant, to follow this,  but on a smaller scale. Cause it has a solid point to avoid "bleeding in" of external concepts/ideas/or such.

### Techniques and Soft Skills

* BASE
* ACID
    * What they mean, and how they related to architectures (monolith vs distributed etc...)
* emergent design and intentional architecture 

## Modelling
    * Go deeper on domain modelling techniques and approaches.

### Data 
* Draw the comparison with your blog on cloud services.
* Operational vs Anlytical data
* Data mesh
* Look at data intensive applications book to see 
* Data vs Application architecture might be a more mainstream approach.

### Concurrency Models
* What is covered in the book

### 7 databases in 7 weeks
* ANy thoughts from there

## Architecture Katas

## The role of patterns in architecture + a list of patterns (might be the parent placeholder for things like the SAGA.)

