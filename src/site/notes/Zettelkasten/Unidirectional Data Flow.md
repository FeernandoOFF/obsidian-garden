---
{"dg-publish":true,"permalink":"/zettelkasten/unidirectional-data-flow/","title":"Unidirectional Data Flow","tags":["status/todo","core/tech/fundamentals/design-patterns"],"created":"2023-10-27T11:44:24.825+01:00"}
---


# Unidirectional Data Flow

## What is Unidirectional Data Flow?

The single source of truth is often used with the Unidirectional Data Flow (**UDF**) pattern. In this pattern, **state** flows in only one direction. The **events** that modify the data flow in the opposite direction.
Events are usually triggered from the lower-scoped types (i.e `UI Component`) until they reach the **SSOT** for the corresponding data type. 

## Relates to
## References
