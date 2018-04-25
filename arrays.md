# Arrays

## New Arrays
Use the literal syntax for creating a new array

**Good**
```javascript
let arr = [];
```
**Bad**
```javascript
let arr = new Array();
```

---

## Destructuring
We prefer destructuring when accessing one or more elements of an array

**Good**
```javascript
let [minPrice, maxPrice] = prices;
```
**Bad**
```javascript
let minPrice = prices[0];
let maxPrice = prices[1];
```
---

## Objects in Arrays
If an array of objects spans multiple lines, each opening and closing curly brace should be on its own line

**Good**
```javascript
let objectInArray = [
  {
    id: 1,
    title: "Senior Developer"
  },
  {
    id: 2,
    title: "Developer"
  },
  {
    id: 3,
    title: "Junior Developer"
  }
]
```
**Bad**
```javascript
let objectInArray = [
  {
    id: 1,
    title: "Senior Developer"
  }, {
    id: 2,
    title: "Developer"
  }, {
    id: 3,
    title: "Junior Developer"
  }
]

// OR

let objectInArray = [
  { id: 1, title: "Senior Developer" },
  { id: 2, title: "Developer" },
  { id: 3, title: "Junior Developer" }
]
```

---

## Array Methods
Always use array methods instead of `for` and `while` loops

- Use `map` when the return value should be an array that matches the order and length of the original array, for example when pulling one attribute from an array of objects

  `let ids = arr.map((a) => a.id))`

- Use `forEach` when you don't need the iterator to return anything, for example if a method should be called on each element in the array

  `arr.forEach((a) => doSomethingTo(a))`

- Use `reduce` when you want to accumulate or aggregate data from an array (for example getting the total price in someone's shopping cart)

  `arr.reduce((prev, curr) => prev + curr.price), 0)`

**Good**
```javascript
let userNames = users.map((u) => u.name);
```
**Bad**
```javascript
let userNames = [];
for(i = 0; i < users.length; i++) {
  userNames.push(users[i].name);
}
```
