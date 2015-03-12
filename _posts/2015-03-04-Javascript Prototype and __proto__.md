---
layout: post
title: Javascript prototype and __proto__
---

In javascript we can use new keyword to create a object from a function (called constructor function in this case) like below

```
function Foo(){  };
var fooInstance=new Foo();
```
The resulting fooInstance will now have a property \__proto__ as below,
```
console.log(fooInstance.__proto__);  //  foo {}
```
The constructor Foo has a property prototype which wich points to a object which will be used to build fooInstance \__proto__
```
console.log(Foo.prototype)  // foo{}
```

Let's create another object as object literal,

```
var objLit={ zoo:1};
console.log(objLit.__proto__); // Object{}
console.log(objLit.prototype); // undefined
````
What happened here is that, whenever we create object using object literal syntax the type of newly created object is Object.
```
console.log(Object.prototype); // Object{}
console.log(typeof Object); //"function"
```
So above Object.prototype is used to create new object's \__proto__ object.

Conclusion:
Only Functions have prototpe proerty which points to a prototype object which will be used to construct \__proto__ of the new 
objects derived from that function.\__proto__ is the actual object that is used in the lookup chain to resolve properties,methods, etc
