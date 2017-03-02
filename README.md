# About Bowtie

Expressive template engine for Node.js heavily inspired by [Jade](http://jade-lang.com/).

## Goals
This project aims to develop an expressive template language to write html documents using the [dry](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) and [kiss](https://en.wikipedia.org/wiki/KISS_principle) principles. And of course, remove the pain of writing angle brackets.
## Current status
This project is currently in it's pre-alpha stage. Current features:
- Loops
- If-Else
- Mixins
- Extending
- Importing

# Getting started
## Installation
```
$ npm install bowtie-js
```
## Syntax highlighting
Syntax highlighting and auto completion is available for [Atom editor](https://atom.io/). Syntax highlighting is triggered on .bow-files.

 Install:
```
$ apm install atom-language-bowtie
```
## Usage with gulp
Gulp compatible compiling comes out of the box with Bowtie, example:
```javascript
var gulp = require('gulp');
var bowtie = require('bowtie-js').gulp;

gulp.task('bowtie', function() {
  return gulp.src('*.bow')
    .pipe(bowtie({
      // Pretty output
      "pretty": true,
      // Object to pass to template engine
      "locals": {
        "title": "Example application"
      }
    }))
    .pipe(gulp.dest('./dist'));
});
```
# Language reference
## Attributes
Attributes are provided in the same way as good old HTML, within parenthesis.
```erlang
a(href="#" role="button"): "Foo bar"
```
Results in
```html
<a href="#" role="button">Foo bar</a>
```
### Class and ID literals
```erlang
div#foo.bar {
  p: "Content"
}
```
```html
<div id="foo" class="bar">
  <p>Content</p>
</div>
```
## Comments
Comments are used as in javascript
```erlang
// comment
```
No multi line comments are available at this point though.
## Conditionals
Conditionals are used as in javascript
```erlang
if (expr) {
  div#foo.bar {
    p: "True!"
  }
} else {
  div#bar.foo {
    p: "False!"
  }
}
```
## Doctype
```erlang
!doctype("html")
```
## Includes
Includes are used by using the `import` keyword
```erlang
html {
  head {
    import "head.bow"
  }
}
```
## Inheritance
## Interpolation
## Iteration
## Mixins
## Tags
