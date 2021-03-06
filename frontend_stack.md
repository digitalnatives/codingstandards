# Frontend Stack

Table of contents:

* Supported Browsers
* Building
* Assets
* CSS
* JavasScript
* General
* Single page applications
* General websites

## Supported Browsers / Versions
Last two versions of the following browsers: ***Chrome, Firefox, iOs Safari, Safari, Opera (after version 15)***, and the following:

* Android - 4+
* IE - 9*, 10+
* Opera - 12

\* *(no animation, transitions )*

**ECMAScript 5** compatility is a must (Function.bind polyfill is an exception)!: http://kangax.github.io/es5-compat-table/

## Building
Use Sprockets or alternatives for bulding, concatenation and minification.

* [Sprockets](https://github.com/sstephenson/sprockets) (Ruby)
* [Mincer](https://github.com/nodeca/mincer) (nodejs)

### Uglifying

* Sprokects compresses assets automaticly.
* Mincer has built in support, it just have to be enabled:
  https://github.com/nodeca/mincer/blob/a027e611104b903a4ca7e60b5f206a423b821877/examples/environment.js#L84

## Assest

### Responsive Images
Use [Picturefill](https://github.com/scottjehl/picturefill) to display images according to media queries (at loading time).

### Icons
Display icons with icon-font instead of images where ever it is possible, because:

* Smaller file size
* Fewer files
* Scaleable
* Colorable

## CSS

### Software
* **[Sass](https://github.com/nex3/sass)** (preprocessor)
  * NodeJS: `npm install node-sass`
  * Ruby: `gem install sass`
  * Rails: `gem "sass"`
* **[Autoprefixer](https://github.com/ai/autoprefixer)** (postprocessor)
  * NodeJS: `npm install autoprefixer`
  * Rails: `gem "autoprefixer-rails"`
  * Ruby: `gem install autoprefixer-rails`

### Style Guide
*Link to sass style guide*

## JavaScript
### Software
* **[CoffeeScript](https://github.com/jashkenas/coffee-script)** (preprocessor)
  * Ruby: `gem install coffee-script`
  * NodeJS: `npm install coffee-script`

### Testing
For unit testing use in a different environment that loads [Mocha](http://visionmedia.github.io/mocha/), an assertion library
and the unit tests.

### Style Guide
*Link to coffeescript style guide*

## General

This section applies to **single page applications** as well as **generic websites**.

### Event Handling
If the application needs to work on desktop, tablet and on mobile devices then events should be attached accordingly:

1. If the device supports **pointer events** use those (pointerenter, pointerleave, etc... (IE10) )
2. If the device supports **touch events** use those (touchend, touchstart, etc...)
3. Otherwise use **mouse events** (mousedown, mousend, etc...)

### Different resolutions
If the application needs to work in multiple devices it should use Media Queries to display the application correctly.

Defualt media queries for devices:

* Mobile:
  `(min-device-width: 320px) and (max-device-width: 480px)`
* Tablet:
  `(min-device-width: 768px) and (max-device-width: 1024px)`
* Desktop:
  `(min-width: 1224px)`
* Larger Screens:
  `(min-width: 1824px)`

### Testing
\# TODO: CasperJS?

## Single Page Applications

### Architecture
Diagram:
[https://docs.google.com/file/d/0B7rerAsh1Hlfd09SdUR5LXVnWGc/edit?usp=sharing](https://docs.google.com/file/d/0B7rerAsh1Hlfd09SdUR5LXVnWGc/edit?usp=sharing)

* **Communication Layer**: This is the layer responsible for communication between the backend and the application, more presicily the model layer. This layer generally use XHR requests to exchange data.
* **SDK Layer**: This layer defines *Models* and *Collections* that use the communication layer. Mostly these are CoffeeScript classes.
* **Display / Interaction Layer**:  This layer handles all user interactions, and the display of the data.

### Routing

Routing is done via **hashtags** and the **hashchange** event. To trigger a change on the site we need to set the **hashtag**.

**Default Routes**:

* ***# TODO***

### Best Practices
* **Modules** - Organize your code into modules
* **Events** - Use events whenever it is convenient
* **Publish/Subscribe** - To connect modules without making dependencies
* **JSON** - Use JSON for data transfer

### Default Stack

* Communication Layer - [jQuery](http://jquery.com/) / [Zepto](http://zeptojs.com/)
* Model Layer - [Backbone.js](http://backbonejs.org/)
* Display / Interaction Layer - [MUI](http://m-ui.org/)

Or: 
* Angular

## Generic Websites

### Architecture
* Display Layer (Browser) - The page is loaded and displayed directly from the server
* Interaction Layer - Interactions are defined after load and they usually few in number

### Rendering
* **Haml** or **JADE**

### Interactions
* JQuery
* DO NOT return JavaScript that runs in the browser, use JSON instead!

