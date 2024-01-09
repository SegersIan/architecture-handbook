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

## General Tips

* Only having additive changes as opposed to destructive ones.

## Mapping Events Between Versions

You can do the mapping logic of an event between versions (e.g. OrderPlaced v1 and v2) on one of these two layers in your stack:
* **Data Layer**: You take an event stream and migrate/copy all this events into a new event stream with a new format. During this process, one can join/split streams and such if desired. This is like a traditional data migration of a database, without editing the table in place, but rather creating a new table where you copy the new version into. In the Application Layer the schema of the event has to be updated to reflect the schema of the new stream. 
* **Application Layer**: You don't change the original events but deal with versioning at run-time on application level.

## Versioning Approaches

| # | Name | Layer | 
| ---  | ---   | --- |
| 1 | Strong Schema - Basic Type Based Versioning | Application |
| 2 | Weak Schema - Mapping | Application |
| 3 | Weak Schema - Wrapper | Application |
| 4 | Negotiation | Application |
| 5 | Copy and Replace | Data | 

### 1. Strong Schema - Basic Type Based Versioning

#### Description

* Explicit versions of a data schema are defined (e.g. v1, v2, ...)
* Data schema is expected to match 1:1 with the serialized type (e.g. WalletCreatedEvent).
* Multiple versions of a single schema are possible, but a type per version is required (e.g. WalletCreatedEvent_v1 and WalletCreatedEvent_v2).
* A new version of an event must be convertible from the old version of the event. If not, it is not a new version of the event but rather a new event.
* Upcasting logic : The logic to convert from an old to a new version is upcasting logic.
* The Ports/Adapters architecture allows you to decouple the version specific type (e.g. WalletCreatedEvent_v1) from your core business logic. Isolating your core from version changes. Alternatively you only pass the latest version (e.g. WalletCreatedEvent_latest), cause any old version should be able to be converted to the latest version.
* Double Publish: Avoid the issues that arise from having old consumers that do not understand the new version of the event. The idea is to have the new version of the producer write both the _v1 and the _v2 versions of the event when it writes. Downstream consumers can decide to ignore the newer version.

#### Pro
* todo...

#### Con
* If versions are not managed, it can become a mess (e.g. WalletCreated_v1 ... WalletCreated_v17) - method explosion.
* Serialize an Enum with a value that is not supported yet in the local strong schema requires dedicated logic.
* All consumers must be updated to understand the schema before a producer is updated.

### 2. Weak Schema - Mapping

#### Description

#### Pro

#### Con
* Serialize an Enum with a value that is not supported yet in the local strong schema requires dedicated logic.

### 3. Weak Schema - Wrapper

#### Description

#### Pro
* Can serialize an Enum with a value that is not supported yet in the local strong schema.

#### Con

### 4. Negotiation

#### Description

#### Pro

#### Con

### 5. Copy And Replace

#### Description

#### Pro

#### Con

## General Concerns

### Versioning Of Behavior

If you find yourself putting branching logic or calculation logic in a projection, especially if it is based on time, you are probably missing logic in the creation of that event.


## Resources

* [Versioning in an Event Sourced System - Gregory Young](https://leanpub.com/esversioning/read)