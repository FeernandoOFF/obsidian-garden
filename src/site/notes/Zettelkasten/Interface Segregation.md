---
{"dg-publish":true,"permalink":"/zettelkasten/interface-segregation/","title":"Interface Segregation","tags":["status/todo","core/tech/fundamentals/principles"],"created":"2023-10-27T12:05:28.822+01:00"}
---


# Interface Segregation

## What is Interfaced Segregation
> Making the interfaces smaller
> Whenever you have a interface being implemented, you need every one of the methods to be used


This principle requires segregating the interfaces within their minimal possible functionality. If there is one object that uses the functionality of another, it should use the maximum of the provided interface. If the module has methods 1, 2, 3, 4, 5 ,6 and one object uses methods 1, 2 and 3 and another object uses methods 4, 5, 6 then probably it makes sense to have two separate interfaces.


## Examples

### Javascript
Classes and inheritance instead of Interfaces
### Kotlin
[[Zettelkasten/Kotlin Syntax#Interfaces\|Kotlin Syntax#Interfaces]]

### Swift
You can achieve this in swift using  [[Zettelkasten/Swift Protocols\|Swift Protocols]]

## Relates to
## References
