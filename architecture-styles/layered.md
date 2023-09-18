# Layered Architecture Style

*Alternative names: n-tier architecture*

## Description

* Good starting point for small, simple applications it websites. It is simple and clean.
* Not ideal for bigger, complex systems.
* Components within the layered architecture style are organized logical horizontal layers, each layer performing a specific role within the application. The amount of layers is not fixed, but 3 or 4 tiers are most common. 
* Physical layering can exist in numerous combinations.
* Each layer has a distinct responsibility and role. Following the seperation of concerns.
* A layer can only call the next layer underneath itself. No skipping layers. A request travels from top to bottom the response the other way up.
* Layers of isolation, changes in a single layer should have no impact or little on the other layers.

## Diagram
![Layered Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1003.png)

## Characteristics Ratings

| Characteristic    | Rating       |
| ---               | ---          |
| Partitioning Type | Technical    |
| Number of quanta  | 1            |
| Deployability     | ⭐           |
| Elasticity        | ⭐           |
| Evolutionary      | ⭐           |
| Fault Tolerance   | ⭐           |
| Modularity        | ⭐           |
| Overall cost      | ⭐⭐⭐⭐⭐ |
| Performance       | ⭐⭐        |
| Reliability       | ⭐⭐⭐      |
| Scalability       | ⭐           |
| Simplicity        | ⭐⭐⭐⭐⭐ |
| Testability       | ⭐⭐        |