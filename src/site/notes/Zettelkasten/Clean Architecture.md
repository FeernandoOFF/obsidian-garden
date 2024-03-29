---
{"dg-publish":true,"permalink":"/zettelkasten/clean-architecture/","title":"Clean Architecture","tags":["status/todo","core/tech"],"dgHomeLink":"false","dgShowBacklinks":"false","dgShowLocalGraph":"false","dgEnableSearch":"false","dgShowTags":"false","created":"2023-10-11T10:29:59.521+01:00"}
---


## What is clean architecture?

Clean architecture is a **set of designs principles** that allow  a separation of software into layers, the main idea is that dependencies should **go from outer layers to inner layers**.

---
## What does it solve?

Clean architecture provides guidelines that allow us to solve common issues in the software industry, such as: 

-  Difficulties in testing
-  Lack of modularity
-  Technology lock-in
-  Poor scalability
-  Lack of clarity and documentation

All of these points are common issues that appear in a software project.


> [!quote] Quote
> It is good to know **clean architecture principles** but it is better to use them wisely otherwise your solution can become overcomplicated with too many unnecessary abstractions and interfaces.


---

## When to choose Clean Architecture
First I'd recommend to define the type of software that you're working on. I'd suggest reading [Five worlds post](https://www.joelonsoftware.com/2002/05/06/five-worlds/) 

1. **Complexity**:  Clean architecture works well with complex systems where there are multiple layers of business logic.
2. **Longevity**: If the project is aiming to evolve and have a long lifespan, clean architecture provides solid guidelines to help the project grow in complexity
3. **Team Size and Collaboration**: Clean Architecture provides clear boundaries and separation of concerns, making it easier for larger teams to work without many conflicts. 
4. **Testability**: Clean architecture promotes testability by enabling unit test of business logic.
5. **Cross-platform Development**: Clean Architecture facilitates cross-platform development by abstracting the core business logic from platform-specific details. This allows to separate interfaces and share the core business logic.
6. **Full-Stack**: If you or your team moves between platforms, clean architecture can allow you to be productive in new projects and start developing without knowing about the specific framework implementation.

---

## When to Not choose Clean Architecture

1. **Small Apps**: For small projects with straightforward requirements and limited complexity, clean architecture may introduce unnecessary overhead and complexity
2. **Tight Deadlines**:  Clean architecture may require additional planning and implementation time. In such cases, a quicker and less complex architecture might be more suitable.
3. **Framework Limitations**:  If the project is tightly coupled to a specific framework or platform that doesn't align well with the principles of clean architecture, it might be more practical to opt for another architecture.


> [!tip] Your app doesn't have to have all of these layers
> Google also recommends a CLEAN-ish architecture, you can see their [architecture guide here](https://developer.android.com/topic/architecture#recommended-app-arch)


---

## Benefits
#### Independent of Framework

When we build a software solution that we want to last long, however, the technology industry is always changing, and all the UI frameworks get new versions every now and then. Clean architecture enables us to switch libraries or frameworks easily, by abstracting them into interfaces and decoupling code.

#### Independence of UI

Independence of the user interface refers to the separation **between the UI** and the **underlying solution or** application. In modern UI development, such as in web apps or mobile applications, **the UI is typically built separately from the core functionality.** However, there may still be **cases where the UI relies on certain business rules** that are implemented within the application itself. By following clean architecture principles, these dependencies can be eliminated or minimized, allowing for a more modular and independent user interface.

#### Testability 

Clean architecture is typically used for projects that aim to **grow over time**. **Testing is crucial** in such projects, especially considering that old projects often **transition to new developers.** Having a reliable source that clearly **defines the business logic and its intended functionality** is essential for ensuring that it continues to work as intended.

---

## Core principles

Clean architecture encourages the use of the following principles:

- [[Zettelkasten/Separation of concerns\|Separation of concerns]]: Avoid overloading a component of functionality. It's better to split it
- [[Zettelkasten/Single source of truth\|Single source of truth]]: Have a single component that allows you to fetch a single class.
- [[Zettelkasten/Unidirectional Data Flow\|Unidirectional Data Flow]]:  The state should go in only one direction.
- [[Zettelkasten/Single Responsibility\|Single Responsibility]]: A class should be responsible for a single, well-defined functionality and should encapsulate that responsibility
- [[Zettelkasten/Open-Closed\|Open-Closed]]: The class should be able to modify its behaviour without modifying the code.
- [[Zettelkasten/Interface Segregation\|Interface Segregation]]: If a class doesn't use an interface, it's better to split it.
- [[Zettelkasten/Dependency Inversion\|Dependency Inversion]]: Business rules should't depend on the framework or UI state.


---

### Concepts
#### [[Zettelkasten/The UI Layer\|The Presentation Layer]]

#### [[Zettelkasten/The Domain layer\|The Domain layer]]

#### [[Zettelkasten/The Data layer\|The Data layer]]


---
## Implementation for different platforms

Examples of how the Clean Architecture concepts and principles can be applied to different technologies and purposes.

##### [[Zettelkasten/Architecture Patterns for Building apps\|Architecture Patterns for Building apps]]
##### [[Clean Principles In iOS Development\|Clean Principles In iOS Development]]
##### [[Zettelkasten/How to structure a Web project\|How to structure a Web project]]
##### [[Zettelkasten/How to structure an Android Project\|How to structure an Android Project]]
##### [[Clean Principles for Web Backend Development\|Clean Principles for Web Backend Development]]


## Relates to

[[Readwise/Articles/Why (And How) You Should Use Feature-Driven Development\|Why (And How) You Should Use Feature-Driven Development]]
[[Zettelkasten/SOLID\|SOLID]]
## References

[Guide app architecture](https://developer.android.com/topic/architecture)
[Clean Architecture - Everything you need to know](https://codilime.com/blog/clean-architecture/#:~:text=Not%20many%20are%20aware%20of,solve%20a%20number%20of%20issues.)
