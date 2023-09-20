# Architecture Styles

Architecture styles can be use for the architecture of a whole system, but these styles can be also combined. One does not exclude the use of others.

As per usual, you need to select the style(s) based on your needs. Remember, as an architect, you must understand your needs for the system.

## Foundations

### (Anti) Patterns

*This section might be moved to a page of it's own, listing all (anti) patterns.

* Big Ball of Mud (Anti Pattern)
    * Absence of architecture, or absence of architecture governance (making sure the vision is followed).
    * No real structure
    * [Orignal Whitepaper](https://www.researchgate.net/publication/2938621_Big_Ball_of_Mud)
* Unitary Architecture (Pattern)
    * System lives on one piece of hardware, no integrations or such.
    * e.g. Embedded systems
* Client/Server (Pattern)
    * Desktop + database server
    * Browser + web server
    * Three-Tier 
* Architecture by implication (Anti Pattern)
* Accident Architecture (Anti Pattern)

### Monolithic vs Distributed Architectures

Neither is better than the other, each answers a specific set of needs. 

### Distributed Architecture Considerations

[Wiki Page](https://en.wikipedia.org/wiki/Fallacies_of_distributed_computing)

The 8 Fallacies:
1. The Network Is Reliable ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0902.png))
2. Latency Is Zero ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0903.png))
3. Bandwith Is Infinite ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0904.png))
4. The Network Is Secure ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0905.png))
5. The Topology Never Changes ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0906.png))
6. There Is Only One Administrator ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0907.png))
7. Transport Cost Is Zero ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0908.png))
8. The Network Is Homogenous ([Illustration](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_0909.png))

Other considerations:
* Distributed logging
* Distributed transactions
* Contract maintenance and versioning (evolution)

### Physical units vs Logical Components

A logical component is a grouping of responsibilities (namespace), the physical units refers to units of deployablility (e.g. JARs or DLLs). Physicall units can still co-exist on the same host. They don't need to be distributted over different hosts.

## Styles Comparison

| Characteristic/Name    | [Layered](layered.md)  |[Pipeline](pipeline.md)   |[Microkernel](microkernel.md)    |[Service-Based](service-based.md)|  [Event-Driven](event-driven.md)|  [Space-Based](space-based.md)    |  [Orchestration-Driven Service-Oriented](orchestration-drive-service-oriented.md)|  [Microservices](microservices.md) |
| ---                    | ---          |---            |---                | ---             | ---              | ---                 | ---                                       | ---                |
| Monolithic/Distributed | Monolithic   | Monolithic    |Monolithic         | Distributed     | Distributed      | Distributed         | Distributed                               | Distributed        |
| Partitioning Type      | Technical    |Technical      | Domain & Technical| Domain          | Technical         | Domain & Technical | Technical                                 | Domain             |
| Number of quanta       | 1            | 1             |1                  |1 to many        | 1 to many         | 1                  | 1                                          | One to many       |
| Deployability          | ⭐           | ⭐⭐        | ⭐⭐⭐           | ⭐⭐⭐⭐      |  ⭐⭐⭐          | ⭐⭐⭐           | ⭐                                        | ⭐⭐⭐⭐         |
| Elasticity             | ⭐           | ⭐           | ⭐                | ⭐⭐           | ⭐⭐⭐          | ⭐⭐⭐⭐⭐       | ⭐⭐⭐                                  | ⭐⭐⭐⭐⭐       |
| Evolutionary           | ⭐           | ⭐⭐⭐      | ⭐⭐⭐           | ⭐⭐⭐         | ⭐⭐⭐⭐⭐     | ⭐⭐⭐           | ⭐                                        | ⭐⭐⭐⭐⭐       |
| Fault Tolerance        | ⭐           | ⭐           | ⭐                | ⭐⭐⭐⭐      |  ⭐⭐⭐⭐⭐    | ⭐⭐⭐            | ⭐⭐⭐                                   | ⭐⭐⭐⭐         |
| Modularity             | ⭐           | ⭐⭐⭐      | ⭐⭐⭐           | ⭐⭐⭐⭐      | ⭐⭐⭐⭐        | ⭐⭐⭐            | ⭐⭐⭐                                  | ⭐⭐⭐⭐⭐       |
| Overall cost           | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐      | ⭐⭐⭐⭐      | ⭐⭐⭐          | ⭐⭐               | ⭐                                       | ⭐                 |
| Performance            | ⭐⭐         | ⭐⭐        | ⭐⭐⭐           | ⭐⭐⭐        | ⭐⭐⭐⭐⭐      | ⭐⭐⭐⭐⭐       | ⭐⭐                                     | ⭐⭐              |
| Reliability            | ⭐⭐⭐      | ⭐⭐⭐      | ⭐⭐⭐           | ⭐⭐⭐⭐      | ⭐⭐⭐          | ⭐⭐⭐⭐          | ⭐⭐                                     | ⭐⭐⭐⭐         |
| Scalability            | ⭐           | ⭐           | ⭐                | ⭐⭐⭐         | ⭐⭐⭐⭐⭐     | ⭐⭐⭐⭐⭐       | ⭐⭐⭐⭐                                | ⭐⭐⭐⭐⭐       |
| Simplicity             | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐         | ⭐⭐⭐        | ⭐               | ⭐                 | ⭐                                        | ⭐                 |
| Testability            | ⭐⭐        | ⭐⭐⭐      | ⭐⭐⭐            |⭐⭐⭐⭐       | ⭐⭐            | ⭐                 | ⭐                                        | ⭐⭐⭐⭐          |

## OThers ...

### Hexagonal (Ports and Adapters) Architecture Style







