[<< Back To Overview](./readme.md)

# Architecture Style: Space-Based

![Space-Based Architecture Style Image](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1502.png)

## Description

This architectural style comes from the notion that in [traditional web faced applications](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1501.png), the database is the ultimate bottleneck which is expensive and complex. When a load of traffic comes in, one would first scale the web servers, afterwards the application servers and last the database servers. So we just move the scaling issue from the front tier to the database tier. For many systems this might not be a real concern, however high-volume applications with large concurrent user load will ultimately run into the database limitations. 

**Space-Based** is specifically designed to address these problems involving high scalability, elasticity, and high concurrency issues. Also useful for applications that have variable, unpredictable concurrent user volume. Solving the extreme and variable scalability issue architecturally is often a better approach than trying to scale out a database or retrofit caching technologies into a nonscalable architecture.

### Topology

Name is based on the concept of *[tuple space](https://en.wikipedia.org/wiki/Tuple_space), the technique of using multiple parallel processors communicating through shared memory.High scalability, high elasticity, and high performance are achieved by removing the central database as a synchronous constrain in the system and instead leveraging replicated in-memory data grids. Applications data is kept in-memory and replicated among all the active *processing units**. When a processing unit updates data, it asynchronously sends that data to the database, usually via messaging with persistent queues. Processing units start up and shut down dynamically as user load increased and decreases, thereby addressing variable scalability. Because there is no central database involved in the standard transactional processing of the application, the database bottleneck is removed, thus providing near-infinite scalability within the application.

There are **5 core architecture components**:
1. **Processing Unit**: Containing the application code
2. **Virtualized Middleware**: To manage and coordinate the processing units
3. **Data Pumps**: To asynchronously send updated data to the database
4. **Data Writers**: To perform the updates from the data pumps
5. **Data Readers**: To read database data and deliver it to the processing units upon startup.

#### 1. Processing Unit (PU)

[Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1503.png)

Contains (entire or portions) of the application logic (including web based components and backend logic). Small webapps might be in a single PU, larger may split functionality in multiple PU based on functional areas. A PU could also be a single-purpose service (e.g. Microservice). If PUs have different logic, then we talk about different PU types. PUs can communicate between each other.

In addition it contains in in-memory data grid and replication engine usually implemented through products like Hazelcast, Apache Ignite or Oracle Coherene.

#### 2. Virtualized Middleware

Handles the infrastructure/operational concerns within the architecture. These components can be self written or COTS.

2.1 **[Messaging Grid]([Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1504.png))**: Manages input request and session state. When a request is received, the messaging grid will decide to which PU the request should be forwarded. This can be round-robin or more complex algorithms, usually implemented using a typical web server with load balancing (e.g. Nginx, HA Proxy).
2.2 **[Data Grid]([Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1505.png))**: Perhaps most crucial and important component. This is the controller for the data grids found in the PU and their synchronization. Based on the data grid, it might be that no "central controller" is required, but usually it is. The idea is that data  is replicated in all PUs. All PUs are aware of each other, and when a (named) cache is updated, that update is propagated immediately across all other PUs. Ensuring all named caches to be in sync.
2.3 **[Processing Grid]([Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1506.png))** [optional]: Responsible for orchestrated request processing, for when a requests needs multiple PU types for processing a request (e.g. Order Processing Unit and Payment Processing Unit).
2.4 **Deployment Manager**: Responsible to shut down or start up new UP based on load. This is your auto-scaling logic.

#### 3. Data Pumps

[Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1507.png)

A processing unit updates its cache, the cache then needs to propagate this to shared cache, and then this change must be propagated to the database. SO this change is send to a data pump. Processing units don't read/write from/to the database. These pumps are usually implemented using messaging. Multiple pumps might exist, dedicated to certain (Sub)-domains or other scope/modelling logic. Pumps usually have associated contracts.

#### 4. Data Writers

[Diagram: General Data Writer](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1508.png)
[Diagram: Dedicated Data Writers](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1509.png)

Accepts the updates from the data pumps and processes them in the database. The granularity of the data writers depend on the scope of the data pumps and processing units. A single data write can also accept from multiple data pumps that all have their own scope.

#### 5. Data Readers

[Diagram](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_1510.png)

Send  reading data from database to processing units via reverse data pump. Data readers are invoked under following situations:
* A crash of all processing units instances of the same named cache
* A redeployment of all processing units within the same named cache
* Retrieving archive data not contained in the replicated cache.

Just like data writers and pumps, these can be scoped on arbitrary domains.

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