# Team Topologies

    Although Team Topologies is strictly not about architecture, it has a huge impact and connection on how we structure team ownership and our architecture according to Conways law. Therefore, I felt this made sense to cover in the Architecture Handbook.

## What is Team Topologies?

"Team Topologies" is a [book](https://teamtopologies.com/book) that provides a framework for organizing and optimizing software development teams within an organization. The book emphasizes the importance of adapting team structures and interactions to the specific context of the organization and its technological landscape. This is all based on the [Reverse Conway Maneuver](https://martinfowler.com/bliki/ConwaysLaw.html). By embracing Conways Law, this framework tries to help create efficient teams that will also result in your desired architecture. As always, frameworks come with their fair share of criticism, but it doesn't make it worth covering and using as input in your decision process.

## Key Concepts

These concepts are used as building blocks on how to reason and think of structuring teams ownership and responsibilities.

### Conway Law

Taking [Conways Law](conways-law.md) in consideration, we can use this to our advantage to create teams that result in the architecture/system that we want, while making the teams also more efficient.

### Flow Of Change

Refers to how changes in software and systems are managed and how they flow through an organization's structure of teams.

[Image: Visual Representation](../attachments/img_team_topologies_flow_of_change.png)

### Team Types

* **Stream-aligned team** aligned to a flow of work from (usually) a segment of the business domain. These are “You Built It, You Run It” teams. No hand-offs to other teams for any purpose.
* **Enabling team** helps a Stream-aligned team to overcome obstacles. Also detects missing capabilities.
* **Complicated Subsystem team** where significant mathematics/calculation/technical expertise is needed.
* **Platform team** a grouping of other team types that provide a compelling internal product to accelerate delivery by Stream-aligned teams

[Image: Visual Representation](../attachments/img_team_topologies_team_types.png)

### Interaction Modes

There are only three ways in which team should interact:

* **Collaboration**: working together for a defined period of time to discover new things (APIs, practices, technologies, etc.) 
* **X-as-a-Service**: one team provides and one team consumes something “as a Service”
* **Facilitation**: one team helps and mentors another team

[Image: Visual Representation](../attachments/img_team_topologies_interaction_modes.png)

## Relation To Systems Thinking

Notice that we recognize the key parts of any generic "system" from [Systems Thinking](./systems-thinking.md).

* **The Organization**: The top level system we view.
* **Team Types**: Are the "Components" or "Elements" that our system is made of up and what their boundaries are.
* **Interaction Modes**: How Components/Elements of a system are interconnected with each other.

## Resources

* [Team Topologies Book](https://teamtopologies.com/book)
* [Team Topologies Website](https://teamtopologies.com/)
* [Talk - Architect for FLow  - DDD & Team Topologies](https://youtu.be/Lfzph_5wb9c?si=01k_bK6HJD7qMYfP) by [Susanne Kaiser](https://www.susannekaiser.net/)
