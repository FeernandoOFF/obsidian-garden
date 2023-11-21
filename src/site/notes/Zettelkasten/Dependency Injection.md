---
{"dg-publish":true,"permalink":"/zettelkasten/dependency-injection/","title":"Dependency Injection","tags":["status/todo","core/tech/android"],"created":"2023-10-27T17:17:15.119+01:00"}
---


# Dependency Injection

### What is dependency injection?

Classes often require references to other classes. For example, a `Car` class might need a reference to an `Engine` class. These required classes are called _dependencies_, and in this example the `Car` class is dependent on having an instance of the `Engine` class to run.

There are three ways for a class to get an object it needs:

1. The class constructs the dependency it needs. In the example above, `Car` would create and initialize its own instance of `Engine`.
2. Grab it from somewhere else. Some Android APIs, such as `Context` getters and `getSystemService()`, work this way.
3. Have it supplied as a parameter. The app can provide these dependencies when the class is constructed or pass them in to the functions that need each dependency. In the example above, the `Car` constructor would receive `Engine` as a parameter.

The third option is dependency injection! With this approach you take the dependencies of a class and provide them rather than having the class instance obtain them itself.

## Example of **not dependency**
Here's an example. Without dependency injection, representing a `Car` that creates its own `Engine` dependency in code looks like this:

```kotlin
class Car {    private val engine = Engine()    fun start() {        engine.start()    }  
}  
  
fun main(args: Array) {    val car = Car()    car.start()  
}
```
![Pasted image 20231027171822.png](/img/user/Files/Pasted%20image%2020231027171822.png)

## Example of dependency
```kotlin
class Car(private val engine: Engine) {    fun start() {        engine.start()    }  
}  
  
fun main(args: Array) {    val engine = Engine()    val car = Car(engine)    car.start()  
}
```
![Pasted image 20231027171909.png](/img/user/Files/Pasted%20image%2020231027171909.png)
## Relates to
[Google's Dependency Injection Guide](https://developer.android.com/training/dependency-injection)
## References
