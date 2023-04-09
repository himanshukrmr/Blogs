---
title: "Understanding “==” (Abstract Equality) and “===” (Strict Equality) in JavaScript"
datePublished: Sun Apr 09 2023 16:03:27 GMT+0000 (Coordinated Universal Time)
cuid: clg9lgn64000c09mifp4l8oki
slug: understanding-abstract-equality-and-strict-equality-in-javascript
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/B3l0g6HLxr8/upload/985c2b902c6b132691c51d5e81d81a4b.jpeg
tags: javascript, coercion, strict-equality-operator, abstract-equality-strict-equality

---

A lot of people including me had a misconception that in JavaScript “==” doesn’t check type and “===” does, but sometimes we have to unlearn some things.

So before understanding these two equalities we have to understand Coercion.

**What is Coercion**

Coercion in JavaScript is the automatic conversion of a value from one data type to another data type.

JavaScript has two types of coercion

* Explicit
    
* Implicit
    

**Explicit coercion** happens when the programmer explicitly converts a value from one type to another, using functions such as `Number()`, `String()`, and `Boolean().`

**Implicit coercion**, on the other hand, happens automatically when JavaScript converts a value to another type behind the scenes.

Examples:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681045779408/a601e741-66af-415f-b332-b5563657096d.png align="center")

Implicit Coercion uses some set of operations that are present in the ECMAScript but they are not available for usage in the ECMAScript.  ie., as developers we cannot use these operations directly. ECMAScript defines several abstract functions including Type, ToPrimitive, ToString, ToNumber, and ToObject for defining the behavior of language constructs and operations.

For the time being let's understand what are **ToPrimitive** and **ToNumber.**

**ToPrimitive** is a built-in abstract operation in JavaScript that converts a value to a primitive value.

Here's how **ToPrimitive** works:

1. If the input value is already a primitive value, return it as-is.
    
2. Otherwise, if the input value has a `valueOf` method that returns a primitive value, call that method and return the result.
    
3. Otherwise, if the input value has a `toString` method that returns a primitive value, call that method and return the result.
    
4. Otherwise, throw a TypeError.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681046147870/63e0289a-12fa-473a-a7c4-7937890eb0e6.png align="center")

In this example, `obj` is an object that has both a `valueOf` method that returns the number `42`, and a `toString` method that returns the string `"foo"`. When we use the `+` operator to add `obj` and `5`, the `ToPrimitive` operation is called on `obj`, with a default hint of "number". The `valueOf` method is called first and returns the primitive value `42`, which is then added to the number `5`, resulting in the number `47`.

**ToNumber** is a built-in abstract operation in JavaScript that converts a value to a number. **ToNumber** takes an input value as its argument and returns a numeric value based on the type and value of the input.

Here's how **ToNumber** works:-

1. If the input value is already a number, return it as-is.
    
2. If the input value is a string, attempt to convert it to a number using the following rules:
    
    * If the string begins with a valid numeric literal (e.g. "123", "-456", "3.14"), parse it into a corresponding number value.
        
    * If the string does not begin with a valid numeric literal, or if it contains characters that cannot be parsed as part of a number (e.g. "foo", "123abc"), return `NaN`.
        
3. If the input value is a boolean, return `1` if the value is `true`, and `0` if the value is `false`.
    
4. If the input value is `null`, return `0`.
    
5. If the input value is `undefined`, return `NaN`.
    
6. If the input value is an object, attempt to call its `valueOf` method. If the result of the method call is a primitive value, return the result after performing `ToNumber` on it. Otherwise, call the object's `toString` method and return the result after performing `ToNumber` on it.
    
7. Otherwise, throw a TypeError.
    

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681046429019/df8bd1c9-e3a9-4b28-9227-e25476fe2aa5.png align="center")

I know it's overwhelming but bear with me 😁

So these are the set of rules which ECMAScript follows for **Abstract Equality Comparison.**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681047490426/91e219aa-ec34-44e6-a656-c8fb03c4da46.png align="center")

As you can see from point number 1 "==" actually checks the type of the numbers which it is comparing, if it is the same then it returns the result after following the rules which **Strict Equality** Comparison follows.

**Now if we follow point number 2 and 3**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681047952131/d4cd7eca-c698-4be6-8202-35e53dfdbe28.png align="center")

we got to know why "null == undefined" is true.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681048089702/ff6703ab-ac25-4485-974e-8589e5875104.png align="center")

**Let's understand point number 4 and 5**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681048189658/0a37dd1f-c41b-45e6-98cb-c52ef65c7b42.png align="center")

Here if any of the two numbers is a string then ECMAScript will prefer a number comparison and converts the string into a number and then do the comparison.

Example:-

`const a = 10;`

`const b = "10";`

`const isEqual = a == b;`

Here isEqual will result in true, as the string "10" is implicitly coerced to the number 10.

**Point number 6 and 7 says that**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681048741955/b20f6fb5-307c-4521-94b2-56becff1c31e.png align="center")

If after doing the above operations, any of the two numbers become boolean or if we are directly doing abstract equality in boolean then it will follow these steps.

*Note:- 'true' is converted to '1 ' and 'false' is converted to '0' during coercion.*

Example:-

`true == 1; // returns true`

`false == 0; // returns true`

`true == "1"; // returns true`

`false == ""; // returns true`

`true == "true"; // returns false`

`false == "false"; // returns false`

**At last, let's understand points 8 and 9**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681049081530/6a14f1e4-ade9-4627-9b19-4b0d21301953.png align="center")

It tells us that if any of the two is an object and the others are string, number or symbol then it will convert the object to a primitive value before doing abstract equality.

Now we understood the rules of **Abstract Equality** let's see the rules which **Strict Equality** comparison follows

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681049476640/b362ad05-ed1b-4174-97bc-82ac7e5e9c66.png align="center")

So in **Strict Equality**, if the type of x is different from the type of y it simply returns false, no coercion is going to happen.

**Now things get interesting from point2**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681053443935/42bacd69-62a1-4ce0-912f-52846ba6562f.png align="center")

we can see if x or y any of them is NaN then it simply returns false as a result we got the answer to why NaN is not equal to NaN.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681055767545/e90d0b39-95e6-4c15-9109-6ba50e8d5dd3.png align="center")

and same for the why +0 is equal to -0

**For the 3rd rule please read below**:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681054154146/382fa329-809a-4cae-9703-214d08c33ac9.png align="center")

here for objects, we have to take some extra note

For Example:-

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1681054479824/ce25e9cb-47bd-43de-ba67-b955902dac77.png align="center")

here we can see that obj1 === obj2 is giving false although the key-value pair is the same, this is because they are 2 different objects pointing/present in a different memory location, so if we compare the same memory objects like obj1 === obj1 as they are present in the same memory location it will result in true.

***Note:****\- We often say JavaScript is weird if we don't understand something about it, due to this it is one of the most hated languages but we also have to understand it is the most loved language also (Quoted Akshay Saini😉). If we know the rules of the language on which it is based then we understand the language better.*

*Peace☮*

*Credits: - I have referred to the official docs of* [*ECMAScript*](https://262.ecma-international.org/10.0/) *for the rules which you are seeing in the blog.*

*Special Thanks! to Sanket Singh by following his lessons I can go this deep into the world of Javascript.*