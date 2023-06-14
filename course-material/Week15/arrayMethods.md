
# Array Methods

Understanding array methods is an important step towards being able to write clean, functional code, and it opens doors to more powerful techniques of functional and reactive programming.


The strength of JavaScript arrays lies in the array methods. Array methods are functions built-in to JavaScript that we can apply to our arrays — Each method has a unique function that performs a change or calculation to our array and saves us from writing common functions from scratch.

---

<br>

### ♦︎ The **`indexOf()`** method

You may want to know the index position of an element in array. You can use the `indexOf()` method to get that. 

```js
const names = ['tom', 'alex', 'bob', 'john'];

names.indexOf('alex'); // returns 1
```
`indexOf()` returns the index of the first occurrence of an element in the array. If an element is not found, the `indexOf()` method returns -1.

```javascript
names.indexOf('rob'); // returns -1
```

----

### ♦︎ **Pop, Push, Shift and unshift Methods**

JavaScript gives us four methods to add or remove items from the beginning or end of arrays:

- **pop()**: Remove an item from the end of an array

```js
let cats = ['Bob', 'Willy', 'Mini'];

cats.pop(); //'Mini'

console.log(cats) //['Bob', 'Willy']
```
> ‣ pop() returns the removed item.

<br>

- **push()**: Add items to the end of an array

```js
let cats = ['Bob'];

cats.push('Willy'); // ['Bob', 'Willy']

cats.push('Puff', 'George'); // ['Bob', 'Willy', 'Puff', 'George']
```
> ‣ push() returns the new array length.

<br>

- **shift()**: Remove an item from the beginning of an array

```js
let cats = ['Bob', 'Willy', 'Mini'];

cats.shift() // 'Bob'
console.log(cats) // ['Willy', 'Mini']
```

> ‣ shift() returns the removed item.

<br>

- **unshift()**: Add items to the beginning of an array

```js
let cats = ['Bob'];

cats.unshift('Willy'); // ['Willy', 'Bob']

cats.unshift('Puff', 'George'); // ['Puff', 'George', 'Willy', 'Bob']

```
> ‣ unshift() returns the new array length.

<br>

<img width="578" alt="Screen Shot 2021-12-15 at 12 25 17 PM" src="https://user-images.githubusercontent.com/47992412/146169616-550f0d7f-370f-4249-9fe4-4ce70b080380.png">

----
