# Unified Sports Data Format
Unified Sports Data Format (USDF) is a schema in which data pertaining to sports fixtures - more specifically sports betting fixtures - can be statelessly encoded from partial deltas into a consistent structure. USDF events can be serialized to JSON, and deserialized into many common weakly and strongly typed languages including, but not limited to Java, Python, R and C#.

A [USDF](UsdfTypes.md) event message comprises of a header, and one or more entries in a partial hierarchy representing changes to state. These deltas can be materialized through the application of a patch to an eventually consistent stateful hierarchy, via a language specific implementation of a stateful directed acyclic graph and a stateless materializer into another sibling format called Unified Sports Materialized Format ([USMF](UsmfTypes.md)). This secondary process does not need to occur in the same application, at the same time, or even in the same technology.

![image](https://user-images.githubusercontent.com/1805709/187051015-b1787fae-7b9e-4510-bf8a-b6bb4b730ff6.png)
