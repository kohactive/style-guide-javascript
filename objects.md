# Objects

## Dot Notation
Use dot notation whenever possible. Even if it causes some inconsistency, it is preferred to use dot notation combined with bracket notation than using only bracket notation

  **Good**
  ```javascript
  ENV.cloudinary = {
    apiKey: "abc123"
  };

  ENV["ember-simple-auth"] = {
    authenticator: "application"
  }
  ```
  **Bad**
  ```javascript
  ENV["cloudinary"] = {
    apiKey: "abc123"
  };

  ENV["ember-simple-auth"] = {
    authenticator: "application"
  }
  ```

---

## Destructuring
Use object destructuring whenever possible in both variable assignment and object creation

**Good**
```javascript
// Assignment
let { name, age, location } = user;

// Object creation
let name = "Anonymous kohactivator";
let age = 30.6;
let location = "Chicago, IL";

let user = { name, age, location };
```
**Bad**
```javascript
// Assignment
let name = user.name;
let age = user.age;
let location = user.location;

// Object creation
let user = {
  name: "Anonymouse kohactivator",
  ago: 30.6,
  location: "Chicago, IL"
}

// Object creation (very bad)
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

## No Trailing ("Dangling") Commas
The last property in an object should not have a trailing comma

  **Good**
  ```javascript
  let dog = {
    goodBoy: true,
    likesCats: false
  };
  ```
  **Bad**
  ```javascript
  let dog = {
    goodBoy: true,
    likesCats: false,
  };
  ```

---

## Property Spacing

One-line properties can be stacked without any padding, but it is recommended to pad functions and other multiline properties with a single empty line

  **Good**
  ```javascript
  let dog = {
    goodBoy: true,
    likesCats: false,

    goForAWalk(length) {
      return walks({ length });
    },

    goForARide() {
      return rolls();
    }
  };
  ```
  **Bad**
  ```javascript
  let dog = {
    goodBoy: true,
    likesCats: false,
    goForAWalk(length) {
      return walks({ length });
    },
    goInTheCar() {
      return rolls();
    }
  };
  ```
