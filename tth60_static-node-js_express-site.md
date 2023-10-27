

# Notes on Template Development
- Link names should not matter they just need to be unique e.g. [Link Lable][a9f]

[a9f]: filename.md/#heading-name

<br><br>



# A Backend Stack: Node.js, Express
Notes covering [Team Treehouse (Code Academy)][M61] coursework for the following:
- *`tthUnitName`* : "Static Node.js and Express Site"
- *`tthUnit`* : 6
- *`associatedTthProjectName`* : "Static Node.js and Express Site"
- *`unitCode`* : backend-stack_node-js_express
- *`filename`* : tth6_backend-stack_node-js_express.md

[M61]: https://teamtreehouse.com

<br><br>



# Table of Contents
1. [Introduction][T61]
1. [The JavaScript Ecosystem][T62]
1. [Node.js Basics](#)
1. [npm Basics](#)
1. [Express Basics](#)
1. [Node and Express Practice](#)
1. [Understanding Express Middleware](#)
1. [Practice ExpressJS: Middleware](#)
1. [Debug Node Applications with Visual Studio Code](#)
1. [Techdegree Strategy Session 2](#)
1. [Static Node.js and Express Site Project](#)

[T61]: #introduction
[T61]: #the-javascript-ecosystem-course
[T62]: #asdf
[T63]: #asdf

<br><br>



# Introduction
- *`section`* : 0
- *`(Node.js, Express) Server-Side Stack`* : make fast, modular, and dynamic web-apps.
- Will use (Node.js, Express, Pug) to build a *`portfolio-site`*.

## Introducing the Static Node.js and Express Site Project (instructionPackage)
- So far, most JS has been (*`client-side`* / in the browser)
- Time for `server-side` JS
- **`First backend project`**

### Portfolio Site
- Modern landing page
- About page
   - Elevator pitch
- Project pages

## First Pass of Project Page (projectPackage)
- Will create a *`JSON file`* to store all the data about the projects (like a mini-database?)
- use *Pug* to complete templates that use JSON to generate markup
- Node.js, Express to:
   - Import required dependencies
   - Link JSON with Pug templates
   - Set routes to handle requests
   - Set up *`middleware`* to use static files like CSS
   - Handle errors
   - Handle requests
   - *`Set up a server`* to serve the project

<br><br>



# The Javascript Ecosystem (course)
- *`section`* : 1
- [ ] How *Node.js* helps JS
- [ ] Find application and tools build with JS
- [ ] Evaluate popular JS frameworks, libraries, developer roles, ...

## JavaScript Outside of the Browser (group)
Node.js provides a way to run JS outside of the browser => can do frontend, server-side dev, native desktop, and mobile applications
- [Client-Side vs. Server-Side JavaScript][611]
- [What is Node.js?][612]
- [Build Native Applications with JavaScript][613]
- [JavaScript Outside of the Browser Review][614]

[611]: #client-side-vs-server-side-javascript-video
[612]: #asdf
[613]: #asdf
[614]: #asdf

## Client-Side vs. Server-Side JavaScript (video)

### General
- JS is the only web-based programming language that can run on both the frontend, and backend.
- Popular, versatile

### Frontend
- Front-end(client-side) JS runs in the browser.  Purpose is to allow user-interaction ( e.g. <mark>form-validation</mark> ) with webpages
   - Improve appearance, and behavior of the rendered webpage
- JS code is interpreted and executed by the browser's JS-engine "against" browser specific APIs like the DOM
   - e.g. for <mark>manipulating elements</mark>

### Backend
- (backend / server-side) JS = code that executes on the server
- "used for building APIs, databases, webservers, ..."
- "Can customize user experience per user"
- Doing both "frontend and backend" development = Full-Stack Dev

### Different Environments
- How can JS run on different environments?
- Different environments will supply JavaScript with [host objects](#) that allow the JS code to execute in that environment
- E.G. browser provides the `window`-host-object so JS can manipulate the DOM along with things like (document, history, XMLHttpRequest, and other host-objects)
- `native objects` built-in objects that are part of the JS- programming-language (e.g. string, number, array, Math) available in ALL environments

### Node
- Server-side runtime environment for JS
- Provides a completely different set of host-objects wrt browser

### Related Tools
- [ ] Node.js
- [ ] Products (app, tools)
- [ ] Frameworks
- [ ] Libraries

### External Links
- [x] [Standard Built-in Objects][615]
- [x] [(Host / Native) Objects][616]
   - [Native JavaScript Object][617]
   - [Host JavaScript Object][617.1]
- [x] [Node.js Basics][618].  Covered later (in this course).
- [x] [JavaScript Landscape][619].  Previously covered.

[615]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects
[616]: https://www.geeksforgeeks.org/what-is-the-difference-between-host-objects-and-native-objects/
[617]: dat-mxe.md/#3ulrg
[617.1]: dat-mxe.md/#ppckv
[618]: https://teamtreehouse.com/library/nodejs-basics-3
[619]: https://teamtreehouse.com/library/the-landscape-of-javascript