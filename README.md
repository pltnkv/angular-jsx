# angular-jsx
Do you use Angular? Are you tired of putting your templates in separate files or trying to escape them in strings?

With the angular-jsx library you can use JSX directly in your directives. JSX templates are converted to strings that Angular can understand.

## Example 1
### Input
```
angular.module("foo").directive("bar",
    function() {
        return {
            template: <div>This is a simple example.</div>
        };
    }
);
```
### Output
```
angular.module("foo").directive("bar",
    function() {
        return {
            template: "<div>This is a simple example.</div>"
        };
    }
);
```
## Example 2
### Input
```
angular.module("foo").directive("bar",
    function() {
        return {
            template: (
                <div>
                    <h1>Multi-line example</h1>
                    <div class="bar">This is a bit more <em>advanced</em>.</div>
                </div>
            )
        }
    }
);
```
### Output
```
angular.module("foo").directive("bar",
    function() {
        return {
            template: (
                "<div>\n    <h1>Multi-line example</h1>\n    <div class=\"bar\">This is a bit more <em>advanced</em>.</div>\n</div>"
            )
        }
    }
);
```
## Usage
```
var angularjsx = require("angular-jsx");
var output = angularjsx.convert(input);
```
