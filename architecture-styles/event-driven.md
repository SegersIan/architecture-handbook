[<< Back To Overview](./readme.md)
 
# Architecture Style: Event-Driven

![Event-Driven Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1401.png)

## Description

Made up of decoupled event processing components that asynchronously receive and process events.
This architectural style can be used standalone or embedded with other architectural styles.

### Request-Based & Event-Based
Majority of processes in any architectural style are request-driven, using the request-based model. 
In the event-based model, systems **react** to an event that happens. We are inversing the responsibility for systems to act accordingly.

If we think about it, the event-model is all around us in nature and physics. When you throw a ball against the wall, the ball moves through the air as reaction to the event of force being excercissed on the ball. 
We could mistake the idea that we "tell the ball" what to do, but rather through our understanding of physics (or experience) we know that the ball will respond with flying through the air, if we put pressure on it.
Actually, in nature there is little that is genuinly "request-based", even a "response" is a reaction to an event that indicated a "request". The philosophical part aside, the request-based model demands a synchronous interaction, event-based is intentionally asynchronous.

### Topologies

Most common topologies are **Broker** and **Mediator** topology. They architecture characteristics and implementation strategy differs between these topologies, therefore it is important to understand the difference between them.

#### Broker Topology (Choreography Pattern)

This is also known as **The Choreography Pattern**.

> Used when you require a high degree of responsiveness and dynamic control over the processing of an event.

This topology has no central event mediator,  messages flow across the event processor components in a chain-like broadcasting fashion. Works great when you have relative simple event processing flow that doesn't require event orchestration and coordination There are [**4 primary architecture components**](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1403.png):

* **Initiating Event**: Event that starts the entire flow. This event gets send to the Event Broker.
    * Example: An order was placed advertised with "PlaceOrder" event.
* **Event Broker**: Receives events and forwards these events based on if any Event Processors are listening and interested for the given even (e,g. through pub/sub).
    * Example: "OrderPlaced" event forwarded to "OrderPlacement"
* **Event Processor**: Accepts an incoming event that it cares about and performs actions/business logic specific to that event. Once the processing is done, the results/output/actions are advertised asynchronously with a Processing Event. Event processors are highly decoupled and independent of each other.
    * Example: "OrderPlacement" processes PlaceOrder event into an order.
* **Processing Event**: 
    * Example: "order-created"

[See Example Flow Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1404.png)

##### Challanges

* No control over the overall workflow associated with the initiating event. Everything is dynamic, based on various conditions, no one in the system really knows when the entire Business activity has been completed or not.
* Error Handling is hard, there is no implicit monitoring if a business activity has failed, or if a failure has occured. Other event processes or not aware of a crash in a certain part of the system.
* The ability to restart a business transaction (recoverability) is also something not supported with this topology. Requiring often manual intervention.












#### Mediator Topology (Orchestration Pattern)

This is also known as **The Orchestration Pattern**.

> Used when you require control over the workflow of an event process

#### Comparison

|                    | Broker/Choreography | Mediator/Orchestration |
| ---                | ---                 | ---                    |
| **Advantages**     | Highly decoupled events processors<br>High scalability<br>High Responsiveness<br>High Performance<br>High fault tolerance |  Workflow control<br>Error handling<br>Recoverability<br>Restart capabilities<br>Better data consistency |
| **Distadvantages** | Workflow control<br>Error handling<br>Recoverability<br>Restart capabilities<br>Data inconsistency | More coupling of event processors<br>Lower Scalability<br>Lower performance<br>Lower fault tolerance<br>Modeling complex workflows |


## When To Use

## When NOT To Use

## Considerations

## Characteristics

| Characteristic    | Rating       |
| ---               | ---          |
| Partitioning Type | Technical    |
| Number of quanta  | 1 to many            |
| Deployability     | ⭐⭐⭐          |
| Elasticity        | ⭐⭐⭐          |
| Evolutionary      | ⭐⭐⭐⭐⭐           |
| Fault Tolerance   | ⭐⭐⭐⭐⭐           |
| Modularity        | ⭐⭐⭐⭐           |
| Overall cost      | ⭐⭐⭐ |
| Performance       | ⭐⭐⭐⭐⭐        |
| Reliability       | ⭐⭐⭐      |
| Scalability       | ⭐⭐⭐⭐⭐           |
| Simplicity        | ⭐ |
| Testability       | ⭐⭐        |

## Resources

* [Building Event-Driven Microservices: Leveraging Organizational Data at Scale](https://www.oreilly.com/library/view/building-event-driven-microservices/9781492057888/)
* [Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/)