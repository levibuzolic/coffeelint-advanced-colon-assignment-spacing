# Coffeelint - Advanced Colon Assignment Spacing [![npm version](https://badge.fury.io/js/coffeelint-advanced-colon-assignment-spacing.svg)](https://www.npmjs.com/package/coffeelint-advanced-colon-assignment-spacing)

> Validate minimum and maximum spacing left and right of a colon assignment.

## Description

This [CoffeeLint](http://www.coffeelint.org) plugin verifies whether or not a minimum amount of spacing is to the left and/or right of a colon assignment. It is based on the 'colon_assignment_spacing' rule but is more powerful allowing you to specify a minimum and maximum allowed spacing. This can come in handy when you have files with object assignments where the colon are vertically aligned. See the Router class in the examples part.
## Installation

```sh
[sudo] npm install -g coffeelint-advanced-colon-assignment-spacing
```
> ***Note:*** *Right now a Coffeelint plugin cannot be installed as a project dependency and must be installed globally. Perhaps this will be improved in a future version of Coffeelint. If you would like to track progress on this enhancement head [over here](https://github.com/clutchski/coffeelint/issues/210).*

## Usage

Insert the below configuration into `coffeelint.json` that you use for linting your scripts:

```json
"advanced_colon_assignment_spacing": {
  "module": "coffeelint-advanced-colon-assignment-spacing",
  "level": "error",
  "spacing": {
    "left": {
      "min": 0,
      "max": 0
    },
    "right": {
      "min": 1,
      "max": null
    }
  }
}
```
## Example

This code will lint without errors:

```
class TestClass

  foo: ->
    bar()

class Router
  routes:
    "/main":            "main"
    "/dashboard/users": "dashboard"
    "/settings":        settings

```

But this will fail:

```
class TestClass

  foo:->
    console.log("Oh no! I have linting errors.")
```

## Configuration

The only configuration option specific to this plugin is the **spacing** property. Change the min/max of the left/right property to control the rule. You can ignore an option by providing `null` instead of an integer.

## Credits
Credits go to [Ian McNally](https://github.com/imcnally) and [Tom Herold](https://github.com/hotzenklotz) whose `colon_assignment_spacing` and `min_colon_spacing` rules serve as the basis for this fork.


## License

[MIT](http://en.wikipedia.org/wiki/MIT_License) © [Levi Buzolic](http://levibuzolic.com)
