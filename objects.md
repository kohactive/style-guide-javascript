# Objects

### Dot Notation
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

### No Trailing ("Dangling") Commas
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

### Property Spacing

One-line properties can be stacked without any padding, but it is recommended to pad functions and other multiline properties with a single empty line

  **Good**
  ```javascript
  let dog = {
    goodBoy: true,
    likesCats: false,

    goForAWalk(length) {
      return this.walks({ length });
    },

    goForARide() {
      return this.rolls();
    }
  };
  ```
  **Bad**
  ```javascript
  let dog = {
    goodBoy: true,
    likesCats: false,
    goForAWalk(length) {
      return this.walks({ length });
    },
    goInTheCar() {
      return this.rolls();
    }
  };
  ```
