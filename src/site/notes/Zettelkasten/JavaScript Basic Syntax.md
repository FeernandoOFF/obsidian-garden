---
{"dg-publish":true,"permalink":"/zettelkasten/java-script-basic-syntax/","title":"JavaScript Basic Syntax","tags":["status/todo"],"noteIcon":"","created":"2023-10-10T17:35:30.092+01:00"}
---


# JavaScript Basic Syntax


### Hello world (Printing & Commenting)
```js
// this is a comment
console.log("Hello world")
/*
 * This is a multiline comment
*/
console.log(`This is an variable ${X} in the log  `)
```
### Variables


> [!NOTE] [[Zettelkasten/JavaScript Basic Syntax#Block scope\|#Block scope]]

```js
var variable = "I can change and im hoisted" // Variable with hoisting
let myName = "I can change" // Variable with blockscope 
const myConst = "I wont change"
```
#### Const
> It does not define a constant value. It defines a constant reference to a value.

Can NOT:
-   Reassign a constant value
-   Reassign a constant array
-   Reassign a constant object

But you CAN:

-   Change the elements of constant array
-   Change the properties of constant object
#### Scope
##### Global scope

> [!NOTE] Scope
> All scripts and functions on a web page can access it.

```js
let carName = "Volvo";  
// code here can use carName  
  
function myFunction() {  
// code here can also use carName  
}
```
##### Block scope
`let,const`: Variables declared inside a { } block cannot be accessed from outside the block:
`var` Variables declared inside a { } block can be accessed from outside the block.
```js
{  
  let x = 2;  
}  
// x can NOT be used here
{  
  var x = 2;  
}  
// x CAN be used here
```

### Operators
- `??`
- `?.` safe call
- `!!`
- `...object` Object spread

### Data Types
#### Number

> [!NOTE] All numbers in JS are always one type: Double (64-bit)

#### BigInt
#### String
#### Boolean
#### Undefined
#### Object
#### Null

##### Null vs Undefined
#### Symbol

### Data Structures
#### Sets

### Functions
- similarities to [[Zettelkasten/Kotlin\|Kotlin]]
- assign variables
```js
function myFunction(param,param,...theRestOfParams){
	return param * param
}

```
#### Anonymous
### Hoisting
### Control Flow
- if
	- ternary
- switch
- for
- 

### Nullability



## Relates to
## References
