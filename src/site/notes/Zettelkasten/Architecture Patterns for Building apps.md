---
{"dg-publish":true,"permalink":"/zettelkasten/architecture-patterns-for-building-apps/","title":"Architecture patterns","tags":["status/todo","core/tech/fundamentals"],"dgHomeLink":"false","dgShowBacklinks":"false","dgShowLocalGraph":"false","dgEnableSearch":"false","dgShowTags":"false","noteIcon":"","created":"2023-10-11T11:53:54.133+01:00"}
---


# Architecture patterns
## Abstract

When researching architecture patterns to  I  encounter a lot of information that turns to be confusing and even more when comparing and switching between platforms, this note aims to give clarification in this regard.


## What are Architecture Patterns

An app has to be planned, and architecture patterns help with that planning process, they are commonly used solutions or approaches for designing the structure and organisation of software. They provide guidelines and best practices that allow to create scalable, maintainable and robust applications. 




> [!NOTE]  [[Zettelkasten/Design Pattern#What is a Design Pattern?\|What is a design pattern?]]



> [!warning] Disclaimer 
> You can have multiple Architecture patterns in a project, this can be within the same layer or different ones


## Most know architecture patterns

Before we dive into the architecture patterns I'd like to section  them in the areas they focus on and I think that [[Zettelkasten/Clean Architecture\|Clean Architecture]] makes the separation  really easily to understand by having a **presentation, data and domain layers** so instead of giving you a full list of architecture patterns I will give you for each area of your app and even how they can interact one with another.

#### The Presentation Layer
- [[Zettelkasten/MVVM\|MVVM]]
- [[MVI\|MVI]]
- [[Component Architecture\|Component Architecture]]
- [[Flux Architecture\|Flux Architecture]]
- [[Zettelkasten/MVC\|MVC]]

#### Data layer

- [[Repository Pattern\|Repository Pattern]]
- [[Data Mapper Pattern\|Data Mapper Pattern]]




---
Separation of concerns
Uni directional flow


## Relates to
[[Architecture Patterns for Building WebApps\|Architecture Patterns for Building WebApps]]

## References

https://medium.com/@pinarkocak/mvc-mvp-and-mvvm-design-patterns-82317d6efeac
https://www.linkedin.com/pulse/mvvm-flux-back-again-andrei-fangli
https://medium.com/@pinarkocak/understanding-viper-pattern-619fa9a0b1f1
