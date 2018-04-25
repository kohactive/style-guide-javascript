# Strings

## Quotes

Use double quotes for all strings. ESLint will enforce this. If you're using a generator (like `ember generate route index`) you can run `npm run lint:js -- --fix` after the generator to convert any single quotes to doubles

**Good**
```javascript
let name = "Bob Dobalina"
```
**Bad**
```javascript
let name = 'Bob Dobalina'
```

---

## Breaking Strings

Don't break long strings onto multiple lines. As Airbnb's style guide says:
> Why? Broken strings are painful to work with and make code less searchable.

**Good**
```javascript
let message = "Holy cow this is gonna be one heckin' long string fren. I wonder how long we can go without using more doggo talkos
```
**Bad**
```javascript
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

---

