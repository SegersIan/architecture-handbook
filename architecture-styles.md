# Architecture Styles

Architecture styles can be use for the architecture of a whole system, but these styles can be also combined. One does not exclude the use of others.

As per usual, you need to select the style(s) based on your needs. Remember, as an architect, you must understand your needs for the system.

## Foundations

### (Anti) Patterns

* Big Ball of Mud
    * Absence of architecture, or absence of architecture governance (making sure the vision is followed).
    * No real structure
    * [Orignal Whitepaper](https://www.researchgate.net/publication/2938621_Big_Ball_of_Mud)
* Unitary Architecture
    * System lives on one piece of hardware, no integrations or such.
    * e.g. Embedded systems
* Client/Server
    * Desktop + database server
    * Browser + web server
    * Three-Tier 

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

## Monolithic Styles

### Layered Architecture Style

![Layered Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1001.png)

### Pipeline Architecture Style

![Pipeline Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1101.png)

### Microkernel Architecture Style

![Microkernel Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1201.png)

### Distributed Styles

## Service-Based Architecture Style

![Service-Based Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1301.png)

## Event-Driven Architecture Style

![Event-Driven Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1401.png)

## Space-Based Architecture Style

![Space-Based Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1501.png)

## Orchestration-Driven Service-Oriented Architecture Style

![Orchestration-Driven Service-Oriented Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1601.png)

## Microservices Architecture Style

![Microservices Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1701.png)
