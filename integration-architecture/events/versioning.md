# Event Versioning

## Why?

To avoid big bang releases.

## Rules

* A new version of an event must be convertible from the old version of the event. If not, it is not a new version of the event but rather a new event.d)
    * Any version of any event should be convertible from any version of a given event. If you find yourself trying to figure out how to convert your old event (Evil Kinevil jumping over a school bus on a motorcycle) to your new version of the event (a monkey eating a banana) and you can’t, this is because you have a new event and not a new version of it.
    * Following this rule you can always upcast.
* At any given point in time, you must only handle the version of the event you understand and ignore all others (to allow for Double Writes, so old and new version is published).


For most systems, a simple human-readable format such as json is fine for handling messages. Most production systems use mapping with either XML or json. Mapping with weak-schema will also remove many of the versioning problems associated with type-based strong schema discussed in the previous chapter.

There are scenarios where, either for performance reasons or in order to enable data to “pass through” without being understood, a wrapper may be a better solution than a mapping, but it will require more code. This methodology is, however, more common with messages, where an enrichment process is occurring, such as in a document-based system.

Overall though, there are very few reasons why it may be considered for the type-based mechanism. Once brought out of your immediate system and put into a serialized form, the type system does very little. The upcasting system is often difficult to maintain amongst consumers; even with a centralized schema repository, it requires another service. In most scenarios where messages are being passed to/from disparate services, late-binding tends to be a better option.






## Resources

* [Versioning in an Event Sourced System - Gregory Young](https://leanpub.com/esversioning/read)