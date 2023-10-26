---
{"dg-publish":true,"permalink":"/zettelkasten/architecture-patterns-for-building-apps/","title":"Architecture patterns","tags":["status/todo","core/tech/fundamentals"],"dgHomeLink":"false","dgShowBacklinks":"false","dgShowLocalGraph":"false","dgEnableSearch":"false","dgShowTags":"false","noteIcon":"","created":"2023-10-11T11:53:54.133+01:00"}
---


# Architecture patterns for building apps
## Abstract

When researching architecture patterns to  I  encounter a lot of information that turns to be confusing and even more when comparing and switching between platforms, this note aims to give clarification in this regard.


## What are Architecture Patterns

An app has to be planned, and architecture patterns help with that planning process, they are commonly used solutions or approaches for designing the structure and organisation of software.

>They provide guidelines and best practices that allow the creation of scalable, maintainable and robust applications. 




> [!NOTE]  [[Zettelkasten/Design Pattern#What is a Design Pattern?\|What is a design pattern?]]

> [!warning] Disclaimer 
> You can have multiple Architecture patterns in a project, this can be within the same layer or different ones

## Core Principles

### Separation of concerns

The **most important** principle to follow is this separation of concerns. A common mistake is to have all the logic inside a UI Element (like a `React Component`, `Android Activity/Fragment` or an `iOS View`), these UI elements should **only contain UI-related logic** and bind user interaction to the state holders that then will update the data that the UI shows to the user.

### Single source of truth

For every data type defined in your app (i.e a `Note` or `User` type) you **should assign** a Single Source of Truth (**SSOT**) to it. So this SSOT is the *owner* of that data and only he can **expose the data using a inmutable type**, and to modify data the SSOT exposes methods that are accessible from other layers. (This should be the `Repository` calling an `API` or `Dao` for a data base).

In an offline-first application, the source of truth for application data is typically a database.

This pattern brings multiple benefits:
- It centralises all the changes to a particular type of data in one place.
- It protects the data so that other types cannot interfere with it.
- It makes changes to the data more traceable. Thus, bugs are easier to spot.

### Unidirectional Data Flow

The single source of truth is often used with the Unidirectional Data Flow (**UDF**) pattern. In this pattern, **state** flows in only one direction. The **events** that modify the data flow in the opposite direction.
Events are usually triggered from the lower-scoped types (i.e `UI Component`) until they reach the **SSOT** for the corresponding data type. 

### Drive UI from data models

If you base your app architecture on data model classes, you make your app more testable and robust.

## Most know architecture patterns

Before we dive into the architecture patterns I'd like to categorise them based on the areas they focus on and I believe that [[Zettelkasten/Clean Architecture\|Clean Architecture]] makes the separation  very easy to understand by having  **presentation, data and domain layers** . 
So instead of a full list of architecture patterns I will give you a list of architectures for each layer and how they can interact with each other.


> [!tip]- See App architecture
 ![Pasted image 20231026145233.png](/img/user/Files/Pasted%20image%2020231026145233.png)

#### The Presentation/UI Layer 

The presentation layer's job is to show data on the screen. Whenever the data changes, the UI should update to reflect these changes.

The Presentation layer is made of two things:
- UI Elements that render the data on the screen, like `Composables/Activities/Fragments` on Android, `Components` in React and `Views` in iOS

- State Holders that hold data, expose UI and handle logic, such as (`ViewModels` or `stores`)

> [!tip]- Contents of the Presentation Layer
> ![Pasted image 20231026153253.png](/img/user/Files/Pasted%20image%2020231026153253.png)


- [[Zettelkasten/MVVM\|MVVM]]
- [[MVI\|MVI]]

- [[Zettelkasten/MVC\|MVC]]

- [[Flux Architecture\|Flux Architecture]]
- [[Component Architecture\|Component Architecture]]

#### Data layer

- [[Repository Pattern\|Repository Pattern]]
- [[Data Mapper Pattern\|Data Mapper Pattern]]




---
Separation of concerns
Uni directional flow


## Relates to
[[Architecture Patterns for Building WebApps\|Architecture Patterns for Building WebApps]]

## References
[Gide to app architecture](https://developer.android.com/topic/architecture#recommended-app-arch)

https://medium.com/@pinarkocak/mvc-mvp-and-mvvm-design-patterns-82317d6efeac
https://www.linkedin.com/pulse/mvvm-flux-back-again-andrei-fangli
https://medium.com/@pinarkocak/understanding-viper-pattern-619fa9a0b1f1
