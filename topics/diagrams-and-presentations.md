# Diagramming and Presenting Architecture

Effective communication is critical to an architect's success. Diagramming and presenting are two critical soft skills for the software architect.

## Pattern: Representational Consistency
The practice of always showing the relationship between parts or an architecture, either in diagrams or presentations, before changing views. This is important when describing an architecture, where you must often show different views of the architecture.

[Diagram Example with Representational Consistency](https://fundamentalsofsoftwarearchitecture.com/images/book/fosa_2101.png)

## Diagramming
The topology of architecture is always of interest to architects and developers because if captures how the structure fits together.

### Anti-Pattern: Irrational Artifact Attachment
Proportional relationship between a person's irrational attachment to some artifact and how long it took to produce. That means one will be more attached to a four-hour diagram than a two-hour one. Using low-tech tools lets teams throw away what's not right. 

### Tool Requirements
Many tools exist, the following requirements are well advised to be productive and efficient in creating diagrams.

* **Layers**: A layer allows the drawer to link a group of items together logically to enable hiding/showing individual layers. Using layers, you can build a comprehensive diagram but hide overwhelming details when they aren't necessary.
* **Stencils/Templates**: Ability to build up a library of stencils/templates of common visual components, often composites of other basic shapes. This allows to create visual consistency within your organization.
* **Magnets**: Represents the places on those shapes where lines snap to connect automatically, providing automatic alignment and other visual niceties.

### Standards

* **UML**: Unified Modeling Language which has many interesting diagram types byt has fallen into disuse. Class and workflow diagrams are probably still most mainstream.
* **C4**: There are 4 views or "layers" of the system
    * *Context*: Entire context of the system, including the roles of users and external dependencies.
    * *Container*: The physical (and often logical) deployment boundaries and containers within the architecture. This view forms a good meeting point for operations and architects.
    * *Component*: This mostly aligns with an architect's view of the system.
    * *Class*: Same as the style of class diagrams from UML.
    * One downside is the inability  to express every kind of design an architecture might undertake. **C4 is best suited for monolithic architectures where the container and component relationships may differ, and it's less suited to distributed architectures.**
* **[ArchiMate](https://www.opengroup.org/archimate-forum/archimate-overview)**: Open source enterprise architecture modeling language to support the description, analysis, and visualization of architecture within and across business domains. The goal of ArchiMate is to be "as small as possible", not to cover every edge case scenario.

### Guidelines

When modelling, build your own style when creating diagrams and feel free to borrow from representations that are particularly effective.

* **Consistency**: Consistency is key
* **Titles**: All the elements of a diagram should have titles or are well known to the audience.
* **Lines**: Should be thick enough to see well. 
    * If lines indicate information flow, use arrows to indicate direction.
    * Different arrow heads might suggest other semantics, be consistent.
    * Sync communication is usually a solid line.
    * Async communication is usually a dotted line.
* **Shapes**: No shapes exists across software development, be consistent within your organization.
* **Labels**: Label each item.
* **Color**: We might often favour monochrome, use color when it helps distinguish artifacts from another.
* **Keys**: If shapes are ambiguous for any reason, include keys to indicate what each shape indicates. (a legend)

## Presenting

We will cover here a few interesting points, but the [Presentation Patterns](https://presentationpatterns.com/) website and book


## Resources

* [Fundamentals of Software Architecture](https://fundamentalsofsoftwarearchitecture.com/) - Chapter 21
* [Presentation Patterns: Techniques of crafting better presentations](https://presentationpatterns.com/)