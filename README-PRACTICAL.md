# JavaScript Interview Questions - PRACTICAL (Intermediate to Senior)

**Modern ES6+ Syntax and Array/Object Manipulation** - Focus on practical coding patterns and modern JavaScript features commonly used in production.

---

## Variable Declaration & Scope

**9. What will be the output**
```js
var a = "xyz";
var a = "pqr";
console.log(a)
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : "pqr"</li>
	<li><b>Reason</b> : Both the variables are declared using "var" keyword with the same name "a". The second variable declaration will override the first variable declaration.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**46. What will be the output**
```js
let x; 
console.log(x);
x = 20;
console.log(x);
x = "John";
console.log(x);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : undefined, 20, John</li>
	<li><b>Reason for first console.log(x)</b> : Since x is declared but not assigned any value yet, so this logs undefined</li>
	<li><b>Reason for second console.log(x)</b> : Now x has been assigned a value 20, so this logs 20</li>
	<li><b>Reason for third console.log(x)</b> : Now the value of x has been changed to "John", so this logs John</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

## Array Spread & Spread Operator

**10. What will be the output**
```js
const arr1 = [1, 2, 3, 4];
const arr2 = [6, 7, 5];
const result = [...arr1, ...arr2];
console.log(result);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : [1, 2, 3, 4, 6, 7, 5]</li>
	<li><b>Reason</b> : Spread operator (...) concatenates the two arrays into "result" array.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**11. What will be the output**
```js
const person1 = { name: 'xyz', age: 21 };
const person2 = { city: 'abc', ...person1 };
console.log(person2);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : { city: 'abc', name: 'xyz', age: 21 }</li>
	<li><b>Reason</b> : Spread operator (...) copies all the properties from person1 into person2.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**1. What will be the output**
```js
let arr = [1, 2, 3, 4, 5, -6, 7];
arr.length = 0;
console.log(arr);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : [ ]</li>
	<li><b>Reason</b> : The length of the array has been set to 0, so the array becomes empty.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**44. What will be the output**
```js
var array = [1,2,3,4,5];
delete array[2];
console.log(array.length);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 5</li>
	<li><b>Reason</b> : "delete" removes the element but does not reindex the array or change its length. It leaves undefined holes in the array</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

## Array Methods (map, filter, indexOf)

**19. What will be the output**
```js
console.log('apple'.split(''));
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : [ 'a', 'p', 'p', 'l', 'e' ]</li>
	<li><b>Reason</b> : split method is used to split a string into an array of substrings based on a specified separator. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**20. What will be the output**
```js
const arr = [2,3,5,2,8,10,5];
console.log(arr.indexOf(5))
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 2</li>
	<li><b>Reason</b> : indexOf method returns the index of the first occurrence of the specified element in the array. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**21. What will be the output**
```js
const array = [8, 18, 28, 38];
const result = array.map(element => element + 2)
               .filter((element) => element > 25);
console.log(result);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : [ 30, 40 ]</li>
	<li><b>Reason</b> : The code increments each element in the array by 2 using map and filters out elements greater than 25 using filter.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**33. What will be the output**
```js
const arr = [11, 0, '', false, 2, 1];
const filtered = arr.filter(Boolean);
console.log(filtered);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : [11, 2, 1]</li>
	<li><b>Reason</b> : filter(Boolean) removes all falsy values (0, "" (empty string), false, null, undefined, and NaN) from the array and keeps truthy ones.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**32. What will be the output**
```js
const arr = [10, -1, 2];
arr.sort((a, b) => a - b);
console.log(arr);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : [-1, 2, 10]</li>
	<li><b>Reason</b> : The compare function (a, b) => a - b sorts the numbers numerically in ascending order.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**22. What will be the output**
```js
function checkValue(value){
    var result = Array.isArray(value);
    console.log(result);
}
checkValue([1,2,3]);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : true</li>
	<li><b>Reason</b> : Array.isArray() method is used to check if the provided value is an array.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**40. What will be the output**
```js
const arr = ["A","B","C","D","E"]
console.log(Object.keys(arr)); 
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : [ '0', '1', '2', '3', '4' ]</li>
	<li><b>Reason</b> : In JavaScript, arrays are a special type of object. Object.keys() on an array returns an array of strings representing the indices of the array elements. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

## Destructuring (Modern ES6+)

**35. What will be the output**
```js
const obj = {
var1: 1,
var2: 2
};
const { var1, var2 } = obj;
console.log(var1, var2);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 1, 2</li>
	<li><b>Reason</b> : Object destructuring extracts the values of var1 and var2 from obj object and prints them using console.log(var1, var2)</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**36. What will be the output**
```js
const user = { 
name: "Surbhi dighe", 
country: "India" 
};
const { name: fullname, country } = user;
console.log(fullname);
console.log(name);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : Surbhi Dighe, ReferenceError: name is not defined</li>
	<li><b>Reason for console.log(fullname)</b> : The name property from user is assigned to a local variable fullname.</li>
	<li><b>Reason for console.log(name)</b> : It gives an error because name was assigned to a local variable fullname and therefore name is not directly accessible.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**37. What will be the output**
```js
const person = {
  firstName: 'Surbhi',
};
const { lastName="dighe" } = person;
console.log(lastName);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : dighe</li>
	<li><b>Reason</b> : The lastName property is not defined in the person object and the destructuring syntax provides a default value ("dighe") to be used when the property is missing.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**38. What will be the output**
```js
const person = {
  firstName: 'Surbhi',
};
const { firstName="Henry"} = person;
console.log(firstName);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : Surbhi</li>
	<li><b>Reason</b> : The `firstName` property in the `person` object has the value 'Surbhi'. The default value "Henry" is ignored because it only applies when the property does not exist or is `undefined`</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

## Operators & Type Conversion

**7. What will be the output**
```js
let f = "8";
let a = 1;
console.log((+f)+a+1);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 10</li>
	<li><b>Reason</b> : The expression (+f) is a shorthand way to convert the string value of f to a number. Therefore, (+f) evaluates to 8.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**17. What will be the output**
```js
let x = 5;
let y = x++;
console.log(y);
console.log(x)
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 5, 6</li>
	<li><b>Reason</b> : The post-increment operator increments and returns the value before incrementing.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**18. What will be the output**
```js
let x = 5;
let y = ++x;
console.log(y);
console.log(x)
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 6, 6</li>
	<li><b>Reason</b> : The pre-increment operator increments and returns the value after incrementing.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**34. What will be the output**
```js
var x = 0;
var y = 10;
if(x){
  console.log(x);
}
if(y){
  console.log(y);
}
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 10</li>
	<li><b>Reason</b> : x = 0 is falsy and doesn't trigger the console.log(x), while y = 10 is truthy and triggers the console.log(y).</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

## Default Parameters & Function Features

**23. What will be the output**
```js
function sum(a=5, b=7){
    return a+b;
}
console.log(sum(undefined, 20));
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 25</li>
	<li><b>Reason</b> : Here, undefined is passed as the value for parameter a, and 20 is passed for parameter b. When any parameter is undefined, the default value is used. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

**51. What will be the output of this code?**
```js
function printName(firstName, lastName) {
    firstName = "Aman";
    lastName = "Bhoria";
    return arguments[0] + " " + arguments[1];
}

let name = printName("John", "Doe");
console.log(name)
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : Aman Bhoria</li>
	<li><b>Reason</b> :In non-strict mode, the arguments object (an array-like object) holds the values passed to the function. When you change the function parameters, the corresponding values in the arguments object are updated as well. In strict mode, this link is removed. As a result, function prints the original values that were passed.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

## Object Methods & Merging

**49. What will be the output**
```js
const obj1 = { a: 1, b: 2 };
const obj2 = { b: 3, c: 4 };

const finalObj = Object.assign({}, obj1, obj2);
console.log(finalObj);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : { a: 1, b: 3, c: 4 }</li>
	<li><b>Reason</b> : When two or more objects are merged: If keys conflict (i.e., the same key exists in multiple objects), the value from the later object overwrites the earlier one.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

## Control Flow

**47. What will be the output**
```js
let text;
switch (1) {
  case 0:
    text = "This is zero";
    break;
  case 1:
    text = "This is one";
  case 2:
    text = "This is two";
    break;
  default:
    text = "No matches found!";
}
console.log(text);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : This is two</li>
	<li><b>Reason</b> : switch(1) means JS looks for a case that matches 1. It finds case 1 & sets text as "This is one". But there is no break, so it keeps going (falls through) into case 2 & overwrites the value.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---practical-intermediate-to-senior)**

---

**Last Updated:** February 9, 2026 | **Target:** Intermediate to Senior Developers
