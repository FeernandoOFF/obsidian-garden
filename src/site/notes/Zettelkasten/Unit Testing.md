---
{"dg-publish":true,"permalink":"/zettelkasten/unit-testing/","title":"Unit Testing","tags":["status/todo","core/tech/testing"],"created":"2023-04-14T11:42:48.239+01:00"}
---


# Unit Testing


### What is Unit testing?

Unit testing is a software testing approach where individual units or components of a software application are tested to determine if they are functioning correctly. It involves testing each unit in isolation to ensure its functionality and identify any defects or errors. Unit testing helps identify issues early in the development process and facilitates easier debugging and maintenance.


#### Tools
##### Android
- JUnit
##### iOS
- XCTEST
##### Web
- Vitest
- Jest

#### Things to consider

- **Fast:** By running directly on your own workstation
- **Easy to Implement:** Not too much setup involved and easy to just test output based on certain input
- **Short scope**: Because they don't work within the OS Framework you won't be able to integrate with it, thinks like clicks and lifecycles are outside of its scope
- **Encourages separation of concerns**: By having to separate the business logic with OS-specific implementations. (A good idea is to create useCases or repositories)
- **Easy to do wrong**: 
### Examples



## Relates to
## References
