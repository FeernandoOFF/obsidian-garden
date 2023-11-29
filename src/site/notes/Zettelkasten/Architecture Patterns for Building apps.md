---
{"dg-publish":true,"permalink":"/zettelkasten/architecture-patterns-for-building-apps/","title":"Architecture patterns for Apps","tags":["status/todo","core/tech/fundamentals"],"dgHomeLink":"false","dgShowBacklinks":"false","dgShowLocalGraph":"false","dgEnableSearch":"false","dgShowTags":"false","created":"2023-10-11T11:53:54.133+01:00"}
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

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/zettelkasten/separation-of-concerns/#what-is-separation-of-concerns-pricniple" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## What is Separation of concerns pricniple?

The **most important** principle to follow is this separation of concerns. A common mistake is to have all the logic inside a UI Element (like a `React Component`, `Android Activity/Fragment` or an `iOS View`), these UI elements should **only contain UI-related logic** and bind user interaction to the state holders that then will update the data that the UI shows to the user.



</div></div>


### Single source of truth

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/zettelkasten/single-source-of-truth/#what-is-single-source-of-truth-principle" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## What is Single source of truth principle?

For every data type defined in your app (i.e a `Note` or `User` type) you **should assign** a Single Source of Truth (**SSOT**) to it. So this SSOT is the *owner* of that data and only he can **expose the data using a inmutable type**, and to modify data the SSOT exposes methods that are accessible from other layers. (This should be the `Repository` calling an `API` or `Dao` for a data base).

In an offline-first application, the source of truth for application data is typically a database.

This pattern brings multiple benefits:
- It centralises all the changes to a particular type of data in one place.
- It protects the data so that other types cannot interfere with it.
- It makes changes to the data more traceable. Thus, bugs are easier to spot.


</div></div>



### Unidirectional Data Flow

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/zettelkasten/unidirectional-data-flow/#what-is-unidirectional-data-flow" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



## What is Unidirectional Data Flow?

The single source of truth is often used with the Unidirectional Data Flow (**UDF**) pattern. In this pattern, **state** flows in only one direction. The **events** that modify the data flow in the opposite direction.
Events are usually triggered from the lower-scoped types (i.e `UI Component`) until they reach the **SSOT** for the corresponding data type. 


</div></div>



### Drive UI from data models

If you base your app architecture on data model classes, you make your app more testable and robust.

## Most know architecture patterns

Before we dive into the architecture patterns I'd like to **categorise them** based on the **areas they focus on** and I believe that [[Zettelkasten/Clean Architecture\|Clean Architecture]] makes the separation  very easy to understand by having  **presentation, data and domain layers** . 
So instead of a full list of architecture patterns I will give you a list of architectures for each layer and how they can interact with each other.


> [!tip]- See App architecture
 ![Pasted image 20231026145233.png|{width=70%}](/img/user/Files/Pasted%20image%2020231026145233.png)

#### The UI Layer
 
<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/zettelkasten/the-ui-layer/#architecture-patterns" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



#### Architecture Patterns

There are multiple Design patterns that can help us avoid common mistakes on the UI layer.
##### [[Zettelkasten/MVVM\|MVVM]]
MVVM is the Go-To in Modern Mobile Development, and it works well by separating the UI data from the UI state, for Complex applications you can use [[MVI\|MVI]]

##### [[Zettelkasten/MVC\|MVC]]
##### [[Zettelkasten/Flux Architecture\|Flux Architecture]]
While MVVM is the option for Mobile development (but not limited to it) Flux architecture is the most used architecture in the web. This mainly because of the complexity and amount of components that a website can have.

---


</div></div>


#### The Data layer

<div class="transclusion internal-embed is-loaded"><a class="markdown-embed-link" href="/zettelkasten/the-data-layer/#architecture-patterns" aria-label="Open link"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="svg-icon lucide-link"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"></path><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"></path></svg></a><div class="markdown-embed">



### Architecture Patterns
- [[Repository Pattern\|Repository Pattern]]
- [[Data Mapper Pattern\|Data Mapper Pattern]]

</div></div>



#### [[Zettelkasten/The Domain layer\|The Domain layer]]

The domain layer just contains pure-logic and no architecture pattern should be necessary as the class is not tided to the app's lifecycle or framework, but here are some recommendations when you need to implement them.

1. **Multiple sources**: If your app uses local and remote resources and you have to make operations on top of them i.e get the newest or merge objects, this is a place where a Domain Layer can help you. A `useCase`  might be of help for you and if the data model is different you can create a common `model` for your dataSources.

2. **Joining Repositories**: If you need to inject multiple repositories and perform repetitive operations on them to join them in your UI layer (such as ViewModel), consider creating a separate `repository` that handles the joining of those two repositories.

## Relates to
[[Architecture Patterns for Building WebApps\|Architecture Patterns for Building WebApps]]

## References
[Guide to app architecture](https://developer.android.com/topic/architecture#recommended-app-arch)

https://medium.com/@pinarkocak/mvc-mvp-and-mvvm-design-patterns-82317d6efeac
https://www.linkedin.com/pulse/mvvm-flux-back-again-andrei-fangli
https://medium.com/@pinarkocak/understanding-viper-pattern-619fa9a0b1f1

[Arc Investigation folder](https://arc.net/folder/B24325E9-451A-490C-9050-FCC4373D9196)