#Front-end Job Interview Questions

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## Table of Contents

  1. [General Questions](#general-questions)
  1. [HTML Questions](#html-questions)
  1. [CSS Questions](#css-questions)
  1. [JS Questions](#js-questions)
  1. [Testing Questions](#testing-questions)
  1. [Performance Questions](#performance-questions)
  1. [Network Questions](#network-questions)
  1. [Coding Questions](#coding-questions)
  1. [Fun Questions](#fun-questions)

## Getting Involved

  1. [Contributors](#contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

#### General Questions:

* What did you learn yesterday/this week?
JSON-LD
* What excites or interests you about coding?
Solving problems
* What is a recent technical challenge you experienced and how did you solve it?
Webpack 2, read the docs
* What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?
User friendliness, XSS, TTFI, metadata, code organization, modern JS practices
* Talk about your preferred development environment.
Webstorm/git/unix
* Which version control systems are you familiar with?
Git, (~mercurial, ~svn)
* Can you describe your workflow when you create a web page?
* If you have 5 different stylesheets, how would you best integrate them into the site?
Webpack bundle them
* Can you describe the difference between progressive enhancement and graceful degradation?
Start simple, work up to more complex vs. ensure happy path can be complete if features missing
* How would you optimize a website's assets/resources?
Webpack
* How many resources will a browser download from a given domain at a time?
1
  * What are the exceptions?
  http2
* Name 3 ways to decrease page load (perceived or actual load time).
SSR, bundle splitting, load order
* If you jumped on a project and they used tabs and you used spaces, what would you do?
editorconfig
* Describe how you would create a simple slideshow page.
HTML, CSS, JS
* If you could master one technology this year, what would it be?
Rust, Go, or Elixir
* Explain the importance of standards and standards bodies.
Set a common target for browsers and developers
* What is Flash of Unstyled Content? How do you avoid FOUC?
When content is loaded before CSS. CSS in <head>, inline styles
* Explain what ARIA and screenreaders are, and how to make a website accessible.
Accessibility standards. Follow ARIA guidelines, use ARIA attributes appropriately, no tabindex=-1
* Explain some of the pros and cons for CSS animations versus JavaScript animations.
CSS animations can be put on the GPU for 60fps. Cannot animate to arbitrary distances.
JS animations are CPU heavy, may be slower than 60fps, can animate arbitrary dimensions.
FLIP animations
* What does CORS stand for and what issue does it address?
Cross Origin Resource Sharing - request data from another domain without JSONP

#### HTML Questions:

* What does a `doctype` do?
Declares the document type, lets browser determine how to parse the HTML
* What's the difference between full standards mode, almost standards mode and quirks mode?
Full standards is strict, almost standards allows frames? Quirks mode allows weird things
* What's the difference between HTML and XHTML?
XHTML is a strict set of HTML. Tags must be closed, etc.
* Are there any problems with serving pages as `application/xhtml+xml`?
Old IE will try to download, stylesheets
* How do you serve a page with content in multiple languages?
utf-8
* What kind of things must you be wary of when design or developing for multilingual sites?
utf-8
* What are `data-` attributes good for?
Ignored by browser parsing engines, can be used to seed information to be fetched later. Valid markup
* Consider HTML5 as an open web platform. What are the building blocks of HTML5?
HTML tags? New tags such as canvas, audio, video
* Describe the difference between a `cookie`, `sessionStorage` and `localStorage`.
cookie is 4kb of text, sessionStorage clears when session ends, localStorage persists
* Describe the difference between `<script>`, `<script async>` and `<script defer>`.
script downloads and parses immediately, defer in the head will wait until DOM is parsed, async is whenever
* Why is it generally a good idea to position CSS `<link>`s between `<head></head>` and JS `<script>`s just before `</body>`? Do you know any exceptions?
FOUC for CSS, let initial HTML load then bootstrap JS for TTFP optimization
Exceptions are for isomorphic/inline styles
* What is progressive rendering?
Transfer chunked encoding?
* Have you used different HTML templating languages before?
Handlebars? Angular HTML templates? JSX

#### CSS Questions:

* What is the difference between classes and IDs in CSS?
IDs are supposed to be unique
* What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?
Reset clears browser specific CSS. Normalizing sets useful defaults. Probably reset, no guarantee defaults are what I want.
* Describe Floats and how they work.
Take block out of flow, float it left or right.
* Describe z-index and how stacking context is formed.
z-index is depth on page. Higher numbers are higher on page
* Describe BFC(Block Formatting Context) and how it works.
Region in which layout occurs, accounting for float and position absolute
* What are the various clearing techniques and which is appropriate for what context?
clear: for clearing floats
* Explain CSS sprites, and how you would implement them on a page or site.
Image map with coordinates, just use them
* What are your favourite image replacement techniques and which do you use when?
<picture> element
* How would you approach fixing browser-specific styling issues?
PostCSS-cssnext
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
Move it offscreen, visbility: hidden
* Have you ever used a grid system, and if so, what do you prefer?
Bootstrap
* Have you used or implemented media queries or mobile specific layouts/CSS?
@media
* Are you familiar with styling SVG?
Yes
* How do you optimize your webpages for print?
Create a print stylesheet
* What are some of the "gotchas" for writing efficient CSS?
Nesting, selectors, specificity
* What are the advantages/disadvantages of using CSS preprocessors?
  * Describe what you like and dislike about the CSS preprocessors you have used.
  Less/Sass/PostCSS - more syntax to learn, but more powerful
* How would you implement a web design comp that uses non-standard fonts?
webfonts, or slap the designer
* Explain how a browser determines what elements match a CSS selector.
Walks the DOM tree for matching attributes
* Describe pseudo-elements and discuss what they are used for.
::before ::after to create entries in CSS without changing markup
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
Box model is how browser decides to calculate element height and width
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
Counts border and padding in total height/width
* List as many values for the display property that you can remember.
none, block, inline, inline-block, table, table-cell, table-row
* What's the difference between inline and inline-block?
inline-block respect top and bottom margins, can set height and width
* What's the difference between a relative, fixed, absolute and statically positioned element?
relative to parent, fixed against body, absolute coordinates of body unless child of a relative, default
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
id, specificity
* What existing CSS frameworks have you used locally, or in production? How would you change/improve them?
Less, Sass, PostCSS, Bootstrap
* Have you played around with the new CSS Flexbox or Grid specs?
A little
* How is responsive design different from adaptive design?
/shrug breakpoints vs flow in context of CSS, but I have a different definition
* Have you ever worked with retina graphics? If so, when and what techniques did you use?
<picture> element
* Is there any reason you'd want to use `translate()` instead of *absolute positioning*, or vice-versa? And why?
Animation

#### JS Questions:

* Explain event delegation
Events are captured on the element they occur and bubble
* Explain how `this` works in JavaScript
Bound to declaring function, reference to function instance
* Explain how prototypal inheritance works
Can-do (instead of class is-a)
* What do you think of AMD vs CommonJS?
/shrug ES6 modules
* Explain why the following doesn't work as an IIFE: `function foo(){ }();`.
Syntax error
  * What needs to be changed to properly make it an IIFE?
  Parens around function foo
* What's the difference between a variable that is: `null`, `undefined` or undeclared?
undeclared is undefined, null must be explicitly set
  * How would you go about checking for any of these states?
  lodash methods
* What is a closure, and how/why would you use one?
Scope that has items from parent scope but doesn't export its scope externally. Revealing module pattern, loop variable assignment
* What's a typical use case for anonymous functions?
Callbacks
* How do you organize your code? (module pattern, classical inheritance?)
ES6 modules
* What's the difference between host objects and native objects?
Native objects are ES spec, host objects are environment specific
* Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?
  first is result of function call, second is object instance
* What's the difference between `.call` and `.apply`?
comma separated arguments vs array
* Explain `Function.prototype.bind`.
Binds this in function to a different context
* When would you use `document.write()`?
Never
* What's the difference between feature detection, feature inference, and using the UA string?
Modernizr
* Explain Ajax in as much detail as possible.
XMLHttpRequest
* What are the advantages and disadvantages of using Ajax?
Lightweight, CORS issues
* Explain how JSONP works (and how it's not really Ajax).
Requests a script, evals it
* Have you ever used JavaScript templating?
  * If so, what libraries have you used?
  JSX
* Explain "hoisting".
Lifting a variable to a higher scope
* Describe event bubbling.
Event bubbles from target up its containers, containers may listen for it
* What's the difference between an "attribute" and a "property"?
attributes should be read-only, properties can be set
* Why is extending built-in JavaScript objects not a good idea?
Don't override natives, then consumers don't know what they do
* Difference between document load event and document DOMContentLoaded event?
document load waits for images
* What is the difference between `==` and `===`?
Inference of types
* Explain the same-origin policy with regards to JavaScript.
Can request from same domain only by default
* Make this work:
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
const duplicate = array => array.concat(array)
* Why is it called a Ternary expression, what does the word "Ternary" indicate?
Three arguments
* What is `"use strict";`? what are the advantages and disadvantages to using it?
slightly stricter checking, no globals
* Create a for loop that iterates up to `100` while outputting **"fizz"** at multiples of `3`, **"buzz"** at multiples of `5` and **"fizzbuzz"** at multiples of `3` and `5`
for (let i=0; i<=100; i++) {
  if (i%3===0 && i%5===0) {
    console.log('fizzbuzz');
  } else if (i%3 === 0) {
    console.log(fizz)
  } else if (i%5 === 0) {
    console.log(buzz)
  } else {
    console.log(i);
  }
}
* Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?
No idea what else is using it
* Why would you use something like the `load` event? Does this event have disadvantages? Do you know any alternatives, and why would you use those?
listen to resource finished loading. Promises
* Explain what a single page app is and how to make one SEO-friendly.
Client side routing, single JS bundle download
Google can execute JS now, but other engines might need noscript content
* What is the extent of your experience with Promises and/or their polyfills?
A lot
* What are the pros and cons of using Promises instead of callbacks?
Easier chaining, no cons
* What are some of the advantages/disadvantages of writing JavaScript code in a language that compiles to JavaScript?
Nicer features/syntax, type checking. Output probably not super optimized
* What tools and techniques do you use debugging JavaScript code?
Chrome Developer Tools
* What language constructions do you use for iterating over object properties and array items?
lodash/reduce, map, filter, forEach
* Explain the difference between mutable and immutable objects.
immutable objects cannot be changed
  * What is an example of an immutable object in JavaScript?
  string
  * What are the pros and cons of immutability?
  Time travel debugging, potential memory leaks
  * How can you achieve immutability in your own code?
  Spread operator, object rest spread
* Explain the difference between synchronous and asynchronous functions.
Synchronous are blocking, async execute on interrupts
* What is event loop?
JS loop, processes things on next tick
  * What is the difference between call stack and task queue
  Call stack keeps firing until empty, task queue picks up on next tick
* Explain the differences on the usage of `foo` between `function foo() {}` and `var foo = function() {}`
  Second is assigning anonymous function to a variable, won't have a name in the call stack

#### Testing Questions:

* What are some advantages/disadvantages to testing your code?
Code quality! Takes time
* What tools would you use to test your code's functionality?
Mocha/chai/sinon
* What is the difference between a unit test and a functional/integration test?
Unit tests unit in isolation, mocking or stubbing dependencies
* What is the purpose of a code style linting tool?
Code quality

#### Performance Questions:

* What tools would you use to find a performance bug in your code?
Profiler in dev tools
* What are some ways you may improve your website's scrolling performance?
Don't scrolljack, remove event listeners
* Explain the difference between layout, painting and compositing.
Layout - figure out sizes and placement
Painting - render the pixels
Compositing - place them in the correct place on the page

#### Network Questions:

* Traditionally, why has it been better to serve site assets from multiple domains?
CDNs cache things, parallelize requests between domains
* Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.
Request -> DNS lookup -> request through backhaul to application server -> application server to w/e (DB, etc.), generate markup -> response to client -> render on client
* What are the differences between Long-Polling, Websockets and Server-Sent Events?
Polling heartbeats a server. Websockets keep an open connection between client and server. Server-Sent are push that interrupt client.
* Explain the following request and response headers:
  * Diff. between Expires, Date, Age and If-Modified-...
  Caching strategies, formatting of how to define cache length
  * Do Not Track
  If site respects, don't identify by browser info
  * Cache-Control
  How long to cache the asset
  * Transfer-Encoding
  chunked, gzip
  * ETag
  cache version of resource
  * X-Frame-Options
  allow to render in frame, iframe, or object
* What are HTTP methods? List all HTTP methods that you know, and explain them.
GET POST PUT DELETE OPTIONS HEAD

#### Coding Questions:

*Question: What is the value of `foo`?*
```javascript
var foo = 10 + '20';
```
'1020'

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```
function add(x,y) { return y ? x + y : function(z) { return x + z } }

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagna hog".split("").reverse().join("");
```
goh angasal a m'i

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```
'bar'

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```
Hello World
ReferenceError

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```
2

*Question: What is the value of `foo.x`?*
```javascript
var foo = {n: 1};
var bar = foo;
foo.x = foo = {n: 2};
```
undefined

*Question: What does the following code print?*
```javascript
console.log('one');
setTimeout(function() {
  console.log('two');
}, 0);
console.log('three');
```
one three two

#### Fun Questions:

* What's a cool project that you've recently worked on?
deux
* What are some things you like about the developer tools you use?
script all the things
* Who inspires you in the front-end community?
Brian Lonsdorf
* Do you have any pet projects? What kind?
meh, St. Paul's website, kinda
* What's your favorite feature of Internet Explorer?
It's dying
* How do you like your coffee?
With cream


#### Contributors:

This document started in 2009 as a collaboration of [@paul_irish](https://twitter.com/paul_irish) [@bentruyman](https://twitter.com/bentruyman) [@cowboy](https://twitter.com/cowboy) [@ajpiano](https://twitter.com/ajpiano)  [@SlexAxton](https://twitter.com/slexaxton) [@boazsender](https://twitter.com/boazsender) [@miketaylr](https://twitter.com/miketaylr) [@vladikoff](https://twitter.com/vladikoff) [@gf3](https://twitter.com/gf3) [@jon_neal](https://twitter.com/jon_neal) [@sambreed](https://twitter.com/sambreed) and [@iansym](https://twitter.com/iansym).

It has since received contributions from over [100 developers](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors).
