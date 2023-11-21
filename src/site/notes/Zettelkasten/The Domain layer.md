---
{"dg-publish":true,"permalink":"/zettelkasten/the-domain-layer/","title":"The Domain layer","tags":["status/todo","core/tech/fundamentals/design-patterns"],"created":"2023-10-27T15:21:31.597+01:00"}
---


# The Domain layer

## What is the domain layer?

The domain layer is **responsable** for encapsulating complex **business logic** or **simple business logic** that needs to be **reused by multiple ViewModels**.


> For the Android apps it makes sense to keep Use Cases optional. Google describes this concern in their [guide](https://developer.android.com/topic/architecture/domain-layer#data-access-restriction). Also worth to check this [article](https://medium.com/androiddevelopers/adding-a-domain-layer-bc5a708a96da)


> [!error] What the domain layer **doesn't do**
>  The domain layer **isn't responsable** for how the **data is displayed**, nor is responsable for **storing and retrieving data**. It just holds **business logic**

In smaller apps most of held in **viewModels** but as the app grows makes sense to store it on 

Is made of interactions or **useCases**, which are single actions or tasks that the app can do

---

## When to use a Domain Layer?

If you have simple CRUD operations it is **perfectly fine to access Repository from the ViewModel** without the Use Case middleware.

Implement only Use Cases which actually introduce some application logic on top of data. They can aggregate data from different sources, transform them or execute some complex processes. **Don't create use cases which just forward the call to the Repository.**

#### Benefits
- It avoids **code duplication** - specially when talking about business logic
- It improves **readability** in state holders or classes that implement it, as they just see like an **API call**
- Avoids large classes by **splitting responsibilities**
### Components of the Domain layer
###### Model
Defines the values that a data model has

###### Repository
Handles multiple data sources (multiple) and determine which one to use in different moments. i.e API and local database

- Interface  that exposes methods for accessing data from whatever datasource
###### Use case
> What in [[Zettelkasten/MVVM\|MVVM]] you do in the viewModel now is a **use case**, allowing you to re-use methods
> Contains the **Business Logic**

This gets inserted in the viewModel as a dependency

Uses repository (from whichever source is coming) and handles the **business logic inside** it


## Implementation


#### Naming
You should make obvious when you're calling a domain layer action, this will greatly improve readability in your dataLayer, for that you can use the following conventions:

> _verb in present tense_ + _noun/what (optional)_ + _UseCase_.

#### Dependencies
They can be dependen from Data layer or other useCases, but never UI Layer

> [!NOTE]- Example
> ![Pasted image 20231027154553.png](/img/user/Files/Pasted%20image%2020231027154553.png)


## Use cases and characteristics
#### They can be instantiated anywhere
By not having a life-cycle, they are attached to the caller's scope, so they can be instantiated  every time we need to call them.

#### Can be used for common tasks
They can encapsulate simple and common business data, like formatting. So they can be usually located in **Utility classes**, or static methods.
But they often are hard to find and tend to have miscellaneous functions without purpose.
By moving it to a useCase justifies their existence and usage.

#### Combine data from Repositories
This can be often used in ViewModels making them larger and complex and makes harder to **Test and reuse**, so by moving them into their own useCases allows them to simplify that logic.

#### Allow access to Data Layer?
When adding useCases to your domain layer still having the UI Layer accessing directly some repositories form the Data Layer you may ask yourself;  _"Should I migrate **all of the business data to a use case?**"_
And the answer to that question may depend on your project and how strict you want your architecture to be, the main benefit of doing so is that It makes **testing ViewModel easier**

While the main drawback is that it forces useCases **everywhere**.

> [!NOTE] Personal recommendation 
> Add usecases only when needed allowing the UI layer to access the Data Layer **as required**.

## Relates to
## References
