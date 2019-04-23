# Typescript Application Style Guides

## Single Responsibility Principle
[Understand this concept](https://en.wikipedia.org/wiki/Single_responsibility_principle). Apply it when writing code to ensure that each construct in code corresponds to accomplishing one task.

## Angular Applications
For [Angular](https://angular.io/) applications the [Angular CLI](https://cli.angular.io/) should be used to generate all projects and basic files/modules. All other typescript files should follow the [Angular Style Guide](https://angular.io/guide/styleguide).

### Local Storage
To prevent untentional sharing of data on local storage use `app-name.variable-name` syntax for naming local storage varaibles.

## Node.js Applications
In general, the larger patterns established in the Angular Style Guide should also be followed in Node.js applications. This includes project organization (folders-by-feature and LIFT), as well as general javascript best practices (minimizing anonymous function usage, single responsibility of files, etc.).

Differences in the Node.js application environment included the following:
- Use ES 2016 to it’s fullest. This includes Classes, Arrow Functions, let/const, async/await, etc. (see the [Javascript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) for further details). Be sure that you fully understand the ES 2016 feature before using it (for example, Arrow Functions do not create a new `this` for the arrow functions, which can be helpful if known).
- Express.js application routes should be built using the [Router](https://expressjs.com/en/4x/api.html#router) feature with nested Routers allowing for flexible routing changes at each feature module level of abstraction.


## Typescript Linting & Beautification
We will use [TSLint](https://palantir.github.io/tslint/) to lint all typescript code. All projects should have a .tslint file in place and all code should pass linting before being committed to the repository. All automated development test commands should also include running of the linter and all text editors used need to have their linting features installed/enabled.

TSLint standard contents (small tweaks may be made as projects require):

[Angular TSLint Example](angular-tslint.json)

[NodeJS TSLint Example](nodejs-tslint.json)

## Typescript Comments & Documentation
Code should be self-documenting. Class names, method names, variables, etc. should have reasonably verbose names that clearly communicate their purposes. Try to write code that sounds like it makes sense when read aloud:

```
expect(myFunction).toHaveBeenCalledWith('function-parameters');
```

Comments should be used sparingly to denote information that is not immediately obvious from the code itself.
