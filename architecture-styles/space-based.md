[<< Back To Overview](./readme.md)

# Architecture Style: Space-Based

![Space-Based Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1502.png)

## Description

This architecural style comes from the notion that in [tradional web faced applications](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1501.png), the database is the ultimate bottleneck which is expensive and complex. When a load of traffic comes in, one would first scale the web servers, afterwards the application servers and last the database servers. So we just move the scaling issue from the front tier to the database tier. For many systems this might not be a real concern, however high-volume applications with large concurrent user load will ultimatly run into the database limitations. 




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