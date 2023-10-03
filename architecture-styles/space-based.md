[<< Back To Overview](./readme.md)

# Architecture Style: Space-Based

![Space-Based Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1502.png)

## Description

This architectural style comes from the notion that in [traditional web faced applications](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1501.png), the database is the ultimate bottleneck which is expensive and complex. When a load of traffic comes in, one would first scale the web servers, afterwards the application servers and last the database servers. So we just move the scaling issue from the front tier to the database tier. For many systems this might not be a real concern, however high-volume applications with large concurrent user load will ultimately run into the database limitations. 

**Space-Based** is specifically designed to address these problems involving high scalability, elasticity, and high concurrency issues. Also useful for applications that have variable, unpredictable concurrent user volume. Solving the extreme and variable scalability issue architecturally is often a better approach than trying to scale out a database or retrofit caching technologies into a nonscalable architecture.

### Topology

Name is based on the concept of *[tuple space](https://en.wikipedia.org/wiki/Tuple_space), the technique of using multiple parallel processors communicating through shared memory.e

### Data Collisions

### Cloud vs On-Premise Implementations

### Replicated vs Distributed Caching

### Near-Cache Considerations

## When To Use

## When NOT To Use

## Considerations

## Characteristics

| Characteristic    | Rating       |
| ---               | ---          |
| Partitioning Type | Domain & Technical    |
| Number of quanta  | 1            |
| Deployability     | ⭐⭐⭐      |
| Elasticity        | ⭐⭐⭐⭐⭐           |
| Evolutionary      | ⭐⭐⭐      |
| Fault Tolerance   | ⭐⭐⭐           |
| Modularity        | ⭐⭐⭐      |
| Overall cost      | ⭐⭐ |
| Performance       | ⭐⭐⭐⭐⭐      |
| Reliability       | ⭐⭐⭐⭐      |
| Scalability       | ⭐⭐⭐⭐⭐           |
| Simplicity        | ⭐ |
| Testability       | ⭐        |

## Resources

None