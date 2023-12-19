---
{"dg-publish":true,"permalink":"/zettelkasten/integration-testing/","title":"Integration Testing","tags":["status/todo","core/tech/testing"],"created":"2023-12-17T01:15:09.000+00:00"}
---


# Integration Testing


### What is integrations testing?
Is a code-related practice. So you’ll have to structure your code in a way that is testable. 

It involves that different components or modules of an system/app work as intended. This can involve APIs, Databases and UI elements. 

#### Tools
##### Android
- Expresso / [[Zettelkasten/Android XML\|Android XML]]
- JUnit
- Mockito 

##### iOS
- XCUITest
- EarlGrey
- XCTEST

##### Web

#### Things to consider 

- Encourages modularity and more plantation 

- **Promotes Modularity**: Encourages a modular and well-structured codebase, as testable components with clear interfaces are easier to integrate and test.


- **Improves Collaboration**: Facilitates collaboration among development teams by ensuring that independently developed components can seamlessly integrate.

- **Complex Setup**: Setting up integration tests can be more complex compared to unit tests, especially if the system has external dependencies like databases or APIs.

- **Slower Execution**: Integration tests often take longer to execute compared to unit tests, potentially slowing down the overall testing process.

- **Easy to debug (not as unit)**: As the test will integrate with the native tools and indicate where something broke. 

- **Maintenance Overhead**: Maintaining integration tests may require effort, especially when there are changes in the system architecture or interfaces, leading to updates in multiple tests.

#### Notes
Expensive 🤑
- Requires to set two code bases
- Requires more Setup 
- Maintenance 


>**My take:**
>-  Not for the use case that Tapadoo as They are often used for larger code bases where modularity of a authentication system or a movement of modules is usual. 
> - Make you a better developer 😉

##### Best practices 

[[Zettelkasten/Separation of concerns\|Separation of concerns]]
[[Zettelkasten/Dependency Injection\|Dependency Injection]]
[[Zettelkasten/Dependency Inversion\|Dependency Inversion]]

## Relates to
## References
