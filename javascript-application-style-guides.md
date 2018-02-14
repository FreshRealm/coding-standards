# Javascript Application Style Guides

## Angular.js Applications
All [Angular.js](https://angularjs.org/) applications should follow the [Angular.js Style Guide](https://github.com/johnpapa/angular-styleguide/blob/master/a1/README.md).

For Angular.js applications that are built using Webpack the following tweaks/allowances should be made compared to the style guide:
1. IIFE should be excluded in our javascript files. This is because Webpack deals with this for us.
1. Module declarations should have the module instance exported via `module.exports`
1. Module names should use the “dash” style of replacing spaces and be in all lowercase. Sub-modules can be named with “dots” separating the name (“main”, “main.shared-filters”, etc).

Front-end controllers and services should have reasonable levels of unit test coverage. The rule of thumb is that if the controller or service has business logic in it, then it should be covered by a unit test. Controllers that are just wiring up front end templates to services and data models likely can have their unit tests skipped.

Front-end features that are of significant value and are customer facing are good candidates for covering with functional/integration tests. Work with the PMs and Senior Engineering team to identify these needs and balance the cost of writing and maintaining the functional/integration tests with their value.

Until some point in the future, ES 2016 (aka ES6) features should not be used in Angular.js applications.

### Useful Angular.js Patterns

#### Shared Angular.js Services/Factories/Etc.
Any Angular.js service/factory/resource/etc. that is shared between different modules should be in their own module. This allows the modules that use the shared service can each require them at module declaration and Angular.js can properly load the modules for unit tests and Webpack can efficiently and accurately build dependency trees.

#### Workflow State Management and Transitions
It is often useful when developing a process workflow in Angular.js with ui-router to have a parent state with a controller that acts as a shared view model (often bound to scope as pvm). This parent state should own the `loadingMsg` attribute, which should be set before any child state begins doing work with the server. It should only be cleared when work with the server has finished (in error handling code for instance). If a state transition occurs it should also be protected by the `loadingMsg` attribute: this hides most of the DOM manipulation and allows for a smooth and consistent user experience through workflows.



## Angular Applications
For [Angular](https://angular.io/) applications the [Angular CLI](https://cli.angular.io/) should be used to generate all projects and basic files/modules. All other typescript files should follow the [Angular Style Guide](https://angular.io/guide/styleguide).

### Local Storage
To prevent untentional sharing of data on local storage use `app-name.variable-name` syntax for naming local storage varaibles.

## Node.js Applications
In general, the larger patterns established in the Angular Style Guide should also be followed in Node.js applications. This includes project organization (folders-by-feature and LIFT), as well as general javascript best practices (minimizing anonymous function usage, single responsibility of files, etc.).

Differences in the Node.js application environment included the following:
- Use ES 2015 to it’s fullest. This includes Classes, Arrow Functions, let/const, etc. (see the [Javascript Documentation](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference) for further details). Be sure that you fully understand the ES 2015 feature before using it (for example, Arrow Functions do not create a new `this` for the arrow functions, which can be helpful if known).
- Express.js application routes should be built using the [Router](https://expressjs.com/en/4x/api.html#router) feature with nested Routers allowing for flexible routing changes at each feature module level of abstraction.


## Javascript Linting & Beautification
We will use [JSHint](http://jshint.com) to lint all javascript code. All projects should have a .jshintrc file in place and all code should pass linting before being committed to the repository. All automated development test commands should also include running of the linter and all text editors used need to have their linting features installed/enabled (for Atom, use [Linter](https://atom.io/packages/linter) & [Linter JSHint](https://atom.io/packages/linter-jshint)).

.jshintrc standard contents (small tweaks may be made as projects require):

```json
{
    "globalstrict": true,
    "strict": true,
    "esversion": 6,
    "node": true,
    "-W086": true,
    "expr": true,
    "mocha": true,
    "unused": true,
    "globals": {
        "console": false,
        "moment": true,
        "confirm": false,
        "async": true,
        "alert": false,
        "document": false,
        "angular": false,
        "should": true,
        "inject": false,
        "Promise": true
    }
}
```

A .jsbeautifyrc file will be added to each javascript project that will allow for easy beautification via editor beautifier packages (for Atom, use [Atom Beautify](https://atom.io/packages/atom-beautify) and enable the JavaScript->Beautify On Save setting).
.jsbeautifyrc standard contents:

```json
{
    "indent_size": 4,
    "indent_char": " ",
    "indent_with_tabs": false,
    "eol": "\n",
    "end_with_newline": true,
    "indent_level": 0,
    "preserve_newlines": true,
    "max_preserve_newlines": 4,
    "space_in_paren": false,
    "space_in_empty_paren": false,
    "jslint_happy": false,
    "space_after_anon_function": true,
    "brace_style": "collapse,preserve-inline",
    "break_chained_methods": false,
    "keep_array_indentation": false,
    "unescape_strings": false,
    "wrap_line_length": 0,
    "e4x": false,
    "comma_first": false,
    "operator_position": "before-newline"
}
```


## Javascript Comments & Documentation
Code should be self-documenting. Class names, method names, variables, etc. should have reasonably verbose names that clearly communicate their purposes.

Comments should be used sparingly to denote information that is not immediately obvious from the code itself.

When needed, we will document our code using the http://usejsdoc.org/ documentation syntax.