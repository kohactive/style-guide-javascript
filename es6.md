# ES6

### Destructuring in Assignment
Use whenever possible

**Good**
```javascript
// Object
let { name, age, location } = user;

// Array
let [minPrice, maxPrice] = prices;
```
**Bad**
```javascript
// Object
let name = user.name;
let age = user.age;
let location = user.location;

// Array
let minPrice = prices[0];
let maxPrice = prices[1];
```

---

### Destructuring in Declaration
Use whenever possible

Let destructuring guide your variable naming in callbacks and other functions

**Good**
```javascript
let name = "Anonymous kohactivator";
let age = 30.6;
let location = "Chicago, IL";

let user = { name, age, location };
```
**Bad**
```javascript
let user = {
  name: "Anonymouse kohactivator",
  ago: 30.6,
  location: "Chicago, IL"
}
```
**Worse**
```javascript
let name = "Anonymous kohactivator";
let age = 30.6;
let location = "Chicago, IL";

let user = {
  name: name,
  age: age,
  location: location
}
```

---

## Fat-arrow Functions
Use unless you need to access the inner scope of the function

**Good**
```javascript
this.store.findRecord("dog", 3)
  .then((dog) => this.set("controller.dog", dog));
```
**Bad**
```javascript
let _this = this;
this.store.findRecord("dog", 3)
  .then(function(dog) {
    _this.set("controller.dog", dog);
  });
```

---

## Array Methods
Always use array methods instead of `for` and `while` loops

- Use `map` when the return value should be an array that matches the length of original, for example when pulling one attribute from an array of objects

  `let ids = arr.map((a) => a.id))`

- Use `forEach` when you don't need the iterator to return anything, for example if an action needs to be performed on each element in the array

  `arr.forEach((a) => doSomethingTo(a))`

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

---

## String Templates
Always use string templates instead of concatenation

**Good**
```javascript
let endpoint = `${ENV.apiPrefix}/posts`;
```
**Bad**
```javascript
let endpoint = ENV.apiPrefix + '/posts';
```
