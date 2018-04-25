# Naming Conventions

## Variables

- Be descriptive with variable names

- Err on the side of verbosity. It's better to be overly clear than unclear

- Don't prefix variables with words like `my` or `this`

- Use `camelCase` when naming variables (no `snake_case`)

## Functions

- Be descriptive with function names

- Be consistent with function names

- Prefix private function names with an underscore `_pushToStore` instead of `pushToStore`

- Variables passed in callback functions can be less descriptive (this is mostly true for rejected promises or any other error handler, a simple `e` will convey an instance of an `Error`)

## Files & Modules

- Use `kebab-case` for file and directory names
