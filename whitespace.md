# Whitespace

It's important for our team to be on the same page when it comes to the whitespace in our code. Most of the benefits come from having to put significantly less cognitive energy into figuring out what the code we write should look like. Additional benefits include cleaner git diffs and code that is easier to visually grep for other kohactive team members

- Indentation should be done with 2 spaces. Not tabs.

- Always include a newline at the end of every file. See [this pull request](https://github.com/kohactive/jsoft-ember/pull/21) for information on how to have our editor do this for you!

- Always remove trailing whitespace at the end of every line. See [this pull request, again](https://github.com/kohactive/jsoft-ember/pull/21) for information on how to have our editor do this for you!

- There should be no more than one consecutive empty line in our code. [ESLint rule](https://eslint.org/docs/rules/no-multiple-empty-lines)

- There should be space around infix operators. [ESLint rule](https://eslint.org/docs/rules/space-infix-ops)

- There should be a space after the initial `//` or `/*` in a comment [ESLint Rule](https://eslint.org/docs/rules/spaced-comment)

- In template strings, there should be no space before the opening or closing curly braces [ESLint Rule](https://eslint.org/docs/rules/template-curly-spacing)

---
---

## Variables and Object Properties

Lists of `let` and `const` variables can be multi-lined and indented. [ESLint Rule](https://eslint.org/docs/rules/indent)

  **Okay**
  ```javascript
  let space,
      time,
      matter;

  const love,
        fear,
        anxiety;
  ```
  **Also Okay**
  ```javascript
  let space;
  let time;
  let matter;
  ```

---

Object properties should not be indented and should only have a single space before their values, such as `foo: bar`

  Don't use additional whitespace to align object properties.

  **Good**
  ```javascript
  this.set("dog", {
    isGoodBoy: true,
    lovesSpaghetti: true
  });
  ```
  **Bad**
  ```javascript
  // Too many spaces after property names
  this.set("dog", {
    isGoodBoy     : true,
    lovesSpaghetti: true
  })

  // Too many spaces before property value
  this.set("dog", {
    isGoodBoy:      true,
    lovesSpaghetti: true
  })

  // Improper alignmnent
  this.set("dog", {
                    isGoodBoy: true,
                    lovesSpaghetti: true
                  });
  })
  ```

---
---

## Blocks

Each block should be padded with 1 empty line. The inside of a block should not have an empty line at the beginning and end.

  **Good**
  ```javascript
  if (!currentUser) {
    throw new Error("You must be logged in!");
  }

  if (currentUser.kohactivated()) {
    return true;
  }

  return false;
  ```
  **Bad**
  ```javascript
  if (!currentUser) {

    throw new Error("You must be logged in!");

  }
  if (currentUser.kohactivated()) {

    return true;

  }
  return false;
  ```

---

## Arrays

There should be no space at the beginning and end of arrays

  **Good**
  ```javascript
  [1, 2, 3, 4]
  ```
  **Bad**
  ```javascript
  [ 1, 2, 3, 4 ]
  ```

---

There should be a space after each item in an array (except for the last item)

  **Good**
  ```javascript
  [1, 2, 3, 4]
  ```
  **Bad**
  ```javascript
  [1,2,3,4]
  ```

---

If there is an array in an array or an object in an array, we don't need to add a space between them

  **Good**
  ```javascript
  // Array in array
  [[1, 2], [3, 4]]

  // Object in array
  [{ hello: "world" }, { goodnight: "moon" }]
  ```
  **Bad**
  ```javascript
  // Array in array
  [ [1, 2], [3, 4] ]

  // Object in array
  [ { hello: "world" }, { goodnight: "moon" } ]
  ```

---

Arrays with 5 or more elements can be split onto multiple lines

  **Okay**
  ```javascript
  [
    "Roscoe",
    "Theo",
    "Blue",
    "Oliver",
    "Chance",
    "Tucker"
  ]
  ```

---
---

## Functions

There should be no space between a function name (or the `function` keyword) and the arguments list

  **Good**
  ```javascript
  // function keyword
  function(model, params) {
    ...
  },

  // Function as object property
  let obj = {
    objFunction(model, params) {
      ...
    }
  };
  ```
  **Bad**
  ```javascript
  // function keyword
  function (model, params) {
    ...
  }

  // Function as object property
  let obj = {
    objFunction (model, params) {
      ...
    }
  }
  ```

---

There should be no space at the beginning or end of the arguments list for a function

  **Good**
  ```javascript
  function(model, params) {
    ...
  }
  ```
  **Bad**
  ```javascript
  function( model, params ) {
    ...
  }
  ```
