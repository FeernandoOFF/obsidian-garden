---
{"dg-publish":true,"permalink":"/zettelkasten/oop-in-java-script/","title":"OOP in JavaScript","tags":["status/todo","status/pre-moc/JavaScript"],"noteIcon":"","created":"2023-10-10T17:46:41.076+01:00"}
---


# OOP in JavaScript


### Classes and objects

> [!warning] Everything in JS comes from the Object Prototype

#### Prototypes

JavaScript is based on *Prototypes*
You can access all the `__prototype` methods from the object instance

#### Object literal
> [!error] The literal objects are instances of the `Object` prototype

```js
let user1 = {
	name: "Fernando",
	surname: "fernando",
	fullName: `${this.name} ${this.surname}`,
	//sayHi: ()=>  {}
	//sayHi() {}
	sayHi: function () {
		console.log(`${this.name} says HI`)
	}
}
```


#### Classes

> [!NOTE]- Syntactic sugar
> Classes in JS does not work the same as other programming languages, and are mostly syntatic sugar to the following syntax
>```js
>	let Employee = function(name) {
>		this.name  = name
>	}
>	Employee.prototype = {
>		doWork() {
>			return `${this.name} works...`
>		}
>	}
> Differences: 
> - Hoisting (Class has to be on top)
>```


```js
// Extends
class Student extends User {
let name;
// Call constructor / you can set your own properties here
	constructor(name,props){
		self.name = name
		super(props)
	}
// O
	publishComment(commentContent) {
		const comment = new Comment({
			content: commentContent,
			role: "Student"
		})
				
		this.comments.push(comment)	
	}
}
```
## Relates to
## References
