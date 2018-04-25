# Functions

## Named Functions
Never declare a function in a non-function block (if, while, etc). Assign the function to a variable instead

**Good**
```javascript
if ()
```

## Default Parameters
Use default parameters rather than mutating parameters

**Good**
```javascript
function assignOptions(opts = {}) {
  // ...
}
```
**Bad**
```javascript
function assignOptions(opts) {
  if (!opts) {
    opts = {};
  }
  // ...
}
```

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

## Promises

Promise returns should be a single line that either returns the same thing the promise resolves or calls a private method that handles the promise's resolved data

**Good**
```javascript
this.get("ajax").post(endpoint, { data })
  .then((result) => result)
  .catch((e) => e);

// OR

this.get("ajax").post(endpoint, { data })
  .then((result) => this._handleResult(result))
  .catch((error) => this._handleError(error));
```
**Bad**
```javascript
this.get("ajax").post(endpoint, { data });
  .then((result) => {
    return result;
  }).catch((e) => {
    return e;
  });

// OR

this.get("ajax").post(endpoint, { data })
  .then((result) => {
    let parsedResult = this.parseResult(result);
    return this.reparsedResult(parsedResult);
  }).catch((e) => {
    let [error] = e.errors.full_messages
    return this.handleError(error);
  })
```
