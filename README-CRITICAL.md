# JavaScript Interview Questions - CRITICAL (Senior Level)

**For 2026 Senior Developer Interviews** - Focus on deep understanding of core concepts that distinguish senior developers from mid-level.

---

## Core Concepts: Hoisting, Scope & Closure

**2. What will be the output** ⭐⭐
```js
x = 10;
console.log(x);
var x;
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 10</li>
	<li><b>Reason</b> : The declaration of the variable x is hoisted to the top of its scope.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**26. What will be the output** ⭐⭐⭐
```js
console.log(printName());
function printName(){
    return "Hi my name is Bob"
}
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : Hi my name is Bob</li>
	<li><b>Reason</b> : Regular functions are hoisted to the top. And you can access and call them even before they are declared. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**27. What will be the output** ⭐⭐⭐
```js
console.log(printName());
const printName = () => {
    return "Hi my name is Bob"
}
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : ReferenceError: Cannot access 'printName' before initialization</li>
	<li><b>Reason</b> : Arrow functions cannot be accessed before they are initialised. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**29. What will be the output** ⭐⭐⭐
```js
function hello(){
console.log(name);
console.log(age);
var name = "Alice";
let age = 21;
}
hello();
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : undefined, ReferenceError: can't access lexical declaration 'age' before initialization"</li>
	<li><b>Reason for console.log(name)</b> : The variable name (declared with var) is hoisted to the top, so JavaScript knows it exists, but it hasn't been assigned a value yet, so it prints undefined</li>
	<li><b>Reason for console.log(age)</b> : The variable age (declared with let) is also hoisted to the top of its scope, but unlike var, it is not initialized until the line where it is declared.</b></li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

---

## Scope & Block Scoping

**5. What will be the output** ⭐⭐⭐
```js
for(let i = 0; i < 10; i++){
    setTimeout(function(){
      console.log("value is " + i);
  })
}
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 10 times "value is" followed by the value of i in each iteration, from 0 to 9</li>
	<li><b>Reason</b> : "let" has a block scope, and a new binding will be created for each iteration. Here, a new variable i is created and has a different value for each iteration of the loop.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**4. What will be the output** ⭐⭐⭐
```js
for(var i = 0; i < 10; i++){
    setTimeout(function(){
      console.log("value is " + i);
  })
}
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 10 times, "value is 10"</li>
	<li><b>Reason</b> : "var" has a function scope, and there will be only one shared binding for the iterations. By the time the setTimeout function gets executed, the for loop has already completed and the value of the variable i is 10.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**8. What will be the output** ⭐⭐
```js
let a = 10;
if(true){
   let a = 20;
   console.log(a, "inside");
}
console.log(a, "outside");
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 20, "inside" and 10, "outside"</li>
	<li><b>Reason</b> : The variable "a" declared inside "if" has block scope and does not affect the value of the outer "a" variable.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**39. What will be the output** ⭐⭐
```js
var a = 10;
let a = 20;
console.log(a)
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : SyntaxError: Identifier 'a' has already been declared</li>
	<li><b>Reason</b> : In Javascript, we cannot redeclare a variable with let if it has already been declared in the same scope. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

---

## Event Loop & Asynchronous Execution

**6. What will be the output** ⭐⭐
```js
function hello() {
  console.log("1");
    setTimeout(() => {
        console.log("2");
    })
  console.log("3");
}
hello();
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : "1" followed by "3", and then after a small delay, "2"</li>
	<li><b>Reason</b> : console.log("1") statement logs "1" to the console. Then setTimeout() function is set to execute the callback function in the next event loop iteration and logs "3" to the console.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**43. What will be the output** ⭐⭐⭐
```js
console.log('Start');

setTimeout(() => {
  console.log('setTimeout');
}, 0);

Promise.resolve().then(() => {
  console.log('Promise');
});

console.log('End');
```
<details>
    <summary><b>View Answer</b></summary>
<ul>    
    <li><b>Output</b> : The console will output in this order -> Start, End, Promise, setTimeout</li>
    <li><b>Reason</b> : The execution order is Synchronous code first, then Microtasks run and the Microtask queue is emptied, then the Macrotasks run in the Task queue/ Callback queue. All the callbacks in the .then(), .catch() and .finally() get into the microtask queue and the other asynchronous operations, go into the WebAPIs first and when they are completed, the callbacks in them go to task queue.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

---

## Reference Semantics & Memory

**3. What will be the output** ⭐⭐⭐
```js
let a = { x: 1, y: 2 }
let b = a;
b.x = 3;
console.log(a);
console.log(b);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : { x: 3, y: 2 } { x: 3, y: 2 }</li>
	<li><b>Reason</b> : 'a' and 'b' both are pointing to the same reference.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**41. What will be the output** ⭐⭐⭐
```js
function modify(obj) {
    obj.name = "Updated";
}
let person = { name: "Original" };
modify(person);
console.log(person.name);

function reassign(obj) {
    obj = { name: "New Object" };
}
reassign(person);
console.log(person.name); 
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : Output of the first console log will be "Updated". Output of the second console log will also be "Updated".</li>
	<li><b>Reason</b> : JS does not allow true pass by reference. It uses call by value for primitives (numbers, strings, booleans, null, undefined and symbols) and call by sharing for objects and arrays. <br> If you modify an object's properties inside a function, the changes will reflect outside the function but if you reassign the object completely inside the function, the original reference will remain unchanged outside.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**28. What will be the output (shallow copy of an object)** ⭐⭐⭐
```js
const userDetails = {
  firstName: "Surbhi",
  lastName: "Dighe",
  age: 20,
  address: {
    city: "Hyderabad",
    country: "India",
  },
};

let cloneUserDetails = { ...userDetails };
//Updating original object
userDetails.age = 22;
userDetails.address.city = "Banglore";

console.log(cloneUserDetails.age); 
console.log(cloneUserDetails.address.city);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 20, "Banglore"</li>
	<li><b>Reason </b> : cloneUserDetails is created by using the spread syntax ({ ...userDetails }). This syntax creates a shallow copy of the userDetails object, meaning that the top-level properties are copied, but nested objects are still referenced.</li>
	<li><b>case 1</b> : Although userDetails.age was changed to 22, cloneUserDetails still holds the original value of 20. This is because the spread syntax only creates a shallow copy, so the age property of cloneUserDetails remains unchanged.</li>
	<li><b>case 2</b> : The nested address object is still referenced by cloneUserDetails, so when the city property of userDetails.address is changed, it reflects in cloneUserDetails.address as well. Therefore, the output is "Banglore".</li>
	</ul>

</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**42. What will be the output** ⭐⭐⭐
```js
let a={ x:1, y: {alpha:10,beta:20} };
let b = {...a};

b.x=101;
b.y.alpha=1001;

console.log(a.x);
console.log(a.y.alpha);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : First console log will output "1". Second console log will output "1001".</li>
	<li><b>Reason</b> : The spread operator provides a shallow copy operation and any objects that are deeply nested in the variable a will still be shared between a as well as b. To make an actual deep copy, use the method structuredClone(a) </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

---

## Type Coercion & Equality

**12. What will be the output** ⭐⭐
```js
console.log(5 < 6 < 7);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : true</li>
	<li><b>Reason</b> : In JavaScript, the < operator evaluates expressions from left to right. First, the expression 5 < 6 is evaluated, resulting in true because 5 is less than 6. Then, the expression true < 7 is evaluated. In this case, JavaScript performs type coercion and converts true to the number 1. Therefore, the expression becomes 1 < 7, which is true.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**13. What will be the output** ⭐⭐
```js
console.log(7 > 6 > 5);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : false</li>
	<li><b>Reason</b> : In JavaScript, the > operator evaluates expressions from left to right. First, the expression 7 > 6 is evaluated, resulting in true because 7 is greater than 6. Then, the expression true > 5 is evaluated. In this case, JavaScript performs type coercion and converts true to the number 1. Therefore, the expression becomes 1 > 5, which is false.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**14. What will be the output** ⭐⭐
```js
console.log(0 == false);
console.log(1 == true);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : true, true</li>
	<li><b>Reason</b> : The == operator converts operands to a common type before making the comparison. In both the cases, the boolean value will be converted to a number, i.e., false is converted to 0 and true is converted to 1. So, the expression 0 == false is equivalent to 0 == 0 and 1 == true is equivalent to 1 == 1.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**15. What will be the output** ⭐⭐
```js
console.log([11, 2, 31] + [4, 5, 6]);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : "11,2,314,5,6"</li>
	<li><b>Reason</b> : The + operator is used for both addition and string concatenation. When you try to concatenate two arrays using the + operator, the arrays are converted to strings and then concatenated together. In this case, the arrays [11, 2, 31] and [4, 5, 6] are converted to strings as "11,2,31" and "4,5,6" respectively. Then, the two strings are concatenated, resulting in "11,2,314,5,6".</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**24. What will be the output** ⭐
```js
console.log(10 + "5");
console.log("5" + 10);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 105, 510</li>
	<li><b>Reason</b> : Since one operand is a string, the + operator performs string concatenation. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**25. What will be the output** ⭐
```js
console.log(10 - "5");
console.log("5" - 10);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 5, -5</li>
	<li><b>Reason</b> : In JavaScript, when the subtraction operator - is used, the operands are converted to numbers before performing the subtraction </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**52. What will be the output of this code?** ⭐
```js
let x = true + false; 
let y = x + 1;

console.log(x, y);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 1, 2</li>
	<li><b>Reason</b> : When + operator is used with boolean values, JavaScript performs implicit type coercion: true is converted to 1 and false is converted to 0.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

---

## Object & Array Comparison

**16. What will be the output** ⭐⭐
```js
console.log({} == {}); 
console.log({} === {});
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : false, false</li>
	<li><b>Reason</b> : When you compare objects using == or ===, it checks if they refer to the exact same object. So even if they are looking same, they are pointing to different memory locations.</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**30. What will be the output** ⭐⭐
```js
const arr1 = [1,2,3];
const arr2 = [1,2,3];
const str = "1,2,3";

console.log(arr1 == str);
console.log(arr1 == arr2);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : true, false</li>
	<li><b>Reason for console.log(arr1 == str)</b> : Javascript compiler performs type conversion. In this case, it converts the array arr1 and the string str to their string representations and then compares them.</li>
	<li><b>Reason for console.log(arr1==arr2) </b> : In Javascript arrays are objects and objects are compared by reference. In this case, arr1 and arr2 are pointing to 2 different memory locations</b></li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**31. What will be the output** ⭐⭐
```js
const a = {x : 1};
const b = {x : 1};
console.log(a === b);
console.log(a.x === b.x)
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : false, true</li>
	<li><b>Reason for console.log(a === b)</b> : This compares whether a and b refer to the exact same object in memory. They are two different objects in memory, so the comparison evaluates to false</li>
	<li><b>Reason for console.log(a.x === b.x)</b> : This compares the x property of objects a and b. Since both a.x and b.x have the same value i.e., 1, so the comparison evaluates to true.</b></li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**45. What will be the output** ⭐⭐
```js
let x = ["a","b","c"];
let y = ["a","b","c"];
let z = y;

console.log(x == y);
console.log(z == y);
console.log(z == x);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : false, true, false (In JS arrays are objects, and objects are compared by reference, not by value)</li>
	<li><b>Reason for console.log(x == y)</b> : x and y are two different arrays stored at different memory locations</li>
	<li><b>Reason for console.log(z == y)</b> : z is assigned to y, so both refer to the same memory location</li>
	<li><b>Reason for console.log(z == x)</b> : z and x are two different arrays stored at different memory locations</li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

**50. What will be the output** ⭐
```js
let a = {};
let b = { key: "abc" };
let c = { key: "efg" };

a[b] = 111;
a[c] = 222;
console.log(a[b]);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : 222</li>
	<li><b>Reason</b> :In JavaScript, using an object as a key in a normal object turns it into a string. That string is usually "[object Object]". So, two different objects like b and c become the same key -> a[b] = 111 & a[c] = 222 becomes a["[object Object]"] = 111 & a["[object Object]"] = 222. Hence, the second value (222) replaces the first one. </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

---

## `this` Context Binding

**48. What will be the output** ⭐⭐⭐
```js
const user = {
    name: 'Aman Bhoria!',
    logMessage() {
        console.log(this.name); // What is logged? 
    }
}; 
setTimeout(user.logMessage, 1000);
```
<details>
	<summary><b>View Answer</b></summary>
<ul>	
	<li><b>Output</b> : undefined</li>
	<li><b>Reason</b> : We've passed the reference in setTimeout not the actual function so as a result it doesn't have the user's context while executing. To get the name we've to pass a callback like: setTimeout(() => user.logMessage(), 1000); </li>
</ul>
</details>

**[:top: Scroll to Top](#javascript-interview-questions---critical-senior-level)**

---

**Last Updated:** February 9, 2026 | **Target:** Senior Developer Interviews
