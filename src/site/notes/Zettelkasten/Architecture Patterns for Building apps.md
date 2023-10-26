---
{"dg-publish":true,"permalink":"/zettelkasten/architecture-patterns-for-building-apps/","title":"Architecture patterns","tags":["status/todo","core/tech/fundamentals"],"noteIcon":"","created":"2023-10-11T11:53:54.133+01:00"}
---


# Architecture patterns
## Abstract

When researching architecture patterns to  I  encounter a lot of information that turns to be confusing and even more when comparing and switching between platforms, this note aims to give clarification in this regard.


## What are Architecture Patterns

An app has to be planned, and architecture patterns help with that planning process, they are commonly used solutions or approaches for designing the structure and organisation of software. They provide guidelines and best practices that allow to create scalable, maintainable and robust applications. 




> [!NOTE]- What are design Patterns?
>  
<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/zettelkasten/design-pattern/#what-is-a-design-pattern" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## What is a Design Pattern?
> Is a proven solution to a common problem

As well as [[Zettelkasten/Architecture Patterns for Building apps\|Architecture Patterns for Building apps]] they provide guidelines and best practices but at a more atomic level inside the app, helping make the code testable, reusable and readable.



</div></div>




> [!warning] Disclaimer 
> You can have multiple Architecture patterns in a project, this can be within the same layer or different ones


## Most know architecture patterns

Before we dive into the architecture patterns I'd like to section  them in the areas they focus on and I think that [[Zettelkasten/Clean Architecture\|Clean Architecture]] makes the separation  really easily to undestand by having a **presentation, data and domain layers** so instead of giving you a full list of architecture patterns I will give you for each area of your app and even how they can interact one with another.

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

## References

https://medium.com/@pinarkocak/mvc-mvp-and-mvvm-design-patterns-82317d6efeac
https://www.linkedin.com/pulse/mvvm-flux-back-again-andrei-fangli
https://medium.com/@pinarkocak/understanding-viper-pattern-619fa9a0b1f1
