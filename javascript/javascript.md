# JavaScript

> JavaScript is an obligatory programming language for anyone who wants to code for the Web since all browsers implement it.

- [JS Foundation](https://js.foundation)

## Basics

- When you pass an argument into a function, you're passing the reference in memory. so if you pass an object or an array they will get changed directly. It won't do that with other typeofs like number or string.
 
- Inside a function, if you are going to use a variable, you have to declare it with var, otherwise it would use a global variable with the same name, and that can insert bugs into the whole javascript code.
  
 
- All numbers in JavaScript are 64bit floating point numbers

### Load script on document ready
```js
document.addEventListener("DOMContentLoaded", function(event) { 
    //Do work
});
```

## Presentation tools

- [Spectacle code slide](https://github.com/thejameskyle/spectacle-code-slide) by theJamesKyle

## Managing currency

- store currency in cents to avoid floating point problems


## Charts

### libraries
- [Chartist](http://gionkunz.github.io/chartist-js/) for pie, lines, bars
- [Cytoscape](http://js.cytoscape.org/) for graphs

## Learning resources

- [progressive web apps](https://developers.google.com/web/ilt/pwa/) by Google


## Bundling tools

- [parceljs](https://parceljs.org) - zero config
- rollup - for libraries
- webpack - for web apps


## Web development

> How to speed up web development?

- CodePen experience with live reload
- Decrease devOps time
- Decrease tool setup time
- Use type checking to enable task automation
- Use type checking to avoid missing case handling
- Enforce unit test coverage
- Leverage GUI for UI development
- Add codemods
- Increase Human-friendly feedback
- Increase AI assistance
- 