

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


```
[ ] (???) First 2 lines below
   - Trailing "..., The" vs Leading "The ..."
   - Disambiguation like Wikipedia? with the disambiguating (dam / #tags) in the title's text?

         # JavaScript Ecosystem, The (TTH, Course)

   - Allow for either option? maybe but AXYS output will be what kind?

         # JavaScript Ecosystem, The
         tags: #TTH, #course

```

# Javascript Ecosystem, The
- `tags` : TTH, course, 6100
---

Expected Learning Outcomes
- [x] How *Node.js* helps JS
- [x] Find application and tools build with JS
- [x] Intro to popular JS frameworks, libraries, developer roles, ...

---

- `container` : 61
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## JavaScript Outside of the Browser
- `tags` : TTH, collection, 6110
---

Node.js provides a way to run JS outside of the browser => can do frontend, server-side dev, native desktop, and mobile applications

### Links
- [Client-Side vs. Server-Side JavaScript][61101]
- [What is Node.js?][61102]
- [Build Native Applications with JavaScript][61103]
- [JavaScript Outside of the Browser Review][61104]

[61101]: #client-side-vs-server-side-javascript-14-video
[61102]: #what-is-nodejs-24-video
[61103]: #build-native-applications-with-javascript-34-video
[61104]: #javascript-outside-of-the-browser-review-44-review

---

- `container` : 6110
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## Client-Side vs. Server-Side JavaScript
- `tags` : TTH, Video, 6111/4
---

### General
- JS is the only web-based programming language that can run on both the frontend, and backend.
- Popular, versatile

### Frontend
- `Front-end(client-side) JS runs in the browser`.  Purpose is to allow user-interaction ( e.g. `form-validation` ) with webpages
   - Improve appearance, and behavior of the rendered webpage
- JS code is interpreted and executed by the `browser's JS-engine` "against" browser `specific APIs` like the DOM
   - e.g. for `manipulating elements`

### Backend
- (backend / server-side) JS = code that `executes on the server`
- "used for building APIs, databases, webservers, ..."
- "Can customize user experience per user"
- Doing both "frontend and backend" development = Full-Stack Dev

### Different Environments
- How can JS run on different environments?
- Different environments will supply JavaScript with `host objects` that allow the JS code to execute in that environment
- E.G. browser provides the `window`-host-object so JS can manipulate the DOM along with things like (document, history, XMLHttpRequest, and other host-objects)

### Native Objects
- `native objects` built-in objects that are part of the JS- programming-language (e.g. string, number, array, Math) available in ALL environments (i.e. available in the browser, and server-side environments like Node.js)

### Node
- Server-side runtime environment for JS
- Provides a completely different set of host-objects wrt browser

### Related Tools
- [ ] Node.js
- [ ] Products (app, tools)
- [ ] Frameworks
- [ ] Libraries

### External Links
- [x] [Standard Built-in Objects][61115]
- [x] [(Host / Native) Objects][61116]
   - [Native JavaScript Object][61117]
   - [Host JavaScript Object][61117.1]
- [x] [Node.js Basics][61118].  Covered later (in this course).
- [x] [JavaScript Landscape][61119].  Previously covered.

[61115]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects
[61116]: https://www.geeksforgeeks.org/what-is-the-difference-between-host-objects-and-native-objects/
[61117]: dat-mxe.md/#3ulrg
[61117.1]: dat-mxe.md/#ppckv
[61118]: https://teamtreehouse.com/library/nodejs-basics-3
[61119]: https://teamtreehouse.com/library/the-landscape-of-javascript

---

- `container` : 6111
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## What is Node.js?
- `tags` : TTH, Video, 6112/4
---

### General
- Can run JS on a web-server using `Node.js`
- Node.js based on Google Chrome's `V8` open-source JavaScript engine
- Although same JavaScript engine (V8), the Chrome-browser and Node.js are two different runtime environments
- Node supplies JS a different set of host-objects wrt browser (e.g. http, https, fs for filesystem, url, os)
- These host-objects allow JS to run outside of browser
- "Driving ecosystem" of free, open-source tools
- `npm` (node package manager) - "allows for sharing and reusing code and software written by other developers in the JS community
   - largest package ecosystem in the world; 700,000 packages
   - help developers setup, and build projects
   - often used as a `taskrunner` to automate:
      - repetitive tasks
      - most of their (built tool chain / build toolchain?)
- Since Node is a runtime-environment(RTE), it does not do much out of the box
   - a Node-framework helps with setup to make the RTE do more
   - a popular framework is `Express`
- `Node and Express`
   - Express allows developers to "build scalable feature rich apps, sites" on top of Node in a web-server
   
### Node.js
- `definition` : "cross-platform runtime environment for developing server-side applications with JavaScript"
- `basedOn` : Google's free, open-source `JavaScript engine`, `V8`
- `canBuild` : command-line tools, frameworks, web-servers
- `goodFor` : "Real-time, multi-user applications handling many simultaneous (events / user-actions)"
   - `goodForExamples`: multiplayer games, collaboration tools, video-conferencing

### Express
- provides built-in tools and functionality to take care of common tasks (e.g. routing, handling requests at different URL paths, serving static files, dynamic templating to render HTML pages)
- can also build (1) REST APIs with Express, (2) Simple servers that talk to browsers

### External Links
- [ ] [nodejs.org][61121]
- [ ] [Chrome V8][61122]
   - [ ] [WebAssembly][61123]
- [ ] [npm][61124]
- [ ] [Express][61125]
- [ ] [7 Node.js Projects][61126]

[61121]: https://nodejs.org/en
[61122]: https://v8.dev/
[61123]: https://webassembly.github.io/spec/core/
[61124]: https://www.npmjs.com/
[61125]: https://expressjs.com/
[61126]: https://blog.teamtreehouse.com/7-awesome-things-can-build-node-js

---

- `container` : 6112
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## Build Native Applications with JavaScript
- `tags` : TTH, Video, 6113/4
---

### General
- Build native cross-platform desktop and mobile apps with (Node, Express)
- Can build creative applications without spending too much time on low-level details of application development

### (Node, Express) Stack Apps
- Can build Interactive `CLI` (apps, interfaces)
   - `examples` : []
      - `Create React App`
      - `Vue-CLI`
      - `Angular-CLI`
      - CLI for `module bundler` Webpack
      - CLI for `task runner` Gulp
   - `allowFor` : [] 
      - quick project setup with (basic / standard) configurations
      - Run, build, test, and deploy to production
      - build native apps that run on iOS, and Android

### React Native Framework
- Don't need objectiv C, C, Swift, or Java
- Build real mobile apps using JavaScript
- `examples` : []
   - AirBnb
   - Instagram
- `appsFor` : []
   - Bloomberg
   - Walmart

### Electron Framework
- Cross-platform desktop applications with just HTML, CSS, and JS
- `examples` : []
   - Visual Studio Code
   - Slack
   - Skype
   - WordPress.com app
   - GitHub desktop app
   - fast, lightweight, ope-source terminal `Hyper`

### React 360 Framework
- easy to build interactive 360deg, and VR experiences with JS alone
- then deploy VR app across web, to desktop, mobile, and VR-devices

### External Links
- [ ] [React Native][61131]
- [ ] [Electron][61132]
- [ ] [Hyper Terminal][61133]
- [ ] [Vercel][61134]
- [ ] [React 360][61135]

[61131]: https://reactnative.dev/
[61132]: https://www.electronjs.org/
[61133]: https://hyper.is/
[61134]: vercel.com
[61135]: https://github.com/facebookarchive/react-360

---

- `container` : 6113
- `hierarchy` : unit.course.collection.activity.item

<br><br>



# JavaScript Outside of the Browser Review
- `tags` : TTH, Review, 6114/4
---

No real notes. Passed (review / quiz / test) on first try.

---

- `container` : 6114
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## JavaScript Frameworks, Libraries, and Developer Roles
- `tags` : TTH, collection, 612
---

Node.js provides a way to run JS outside of the browser => can do frontend, server-side dev, native desktop, and mobile applications

### Links
- [JavaScript Frameworks and Libraries][61201]
- [Testing JavaScript][61202]
- [Different Types of JavaScript Developers, The][61203]
- [Frameworks, Libraries, and Developer Roles Review][61204]

[61201]: #client-side-vs-server-side-javascript-14-video
[61202]: #what-is-nodejs-24-video
[61203]: #build-native-applications-with-javascript-34-video
[61204]: #javascript-outside-of-the-browser-review-44-review

---

- `container` : 6120
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## JavaScript Frameworks and Libraries
- `tags` : TTH, Video, 6121/4
---

### Links


---

- `container` : 6121
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## templateItemTitle
- `tags` : fffff
---

### Links
- [linka][aaaaa]
- [linkb][bbbbb]
- [linkc][ccccc]
- [linkd][ddddd]
- [linke][eeeee]

[aaaaa]: #
[bbbbb]: #
[ccccc]: #
[ddddd]: #
[eeeee]: #

---

- `container` : fffff
- `hierarchy` : unit.course.collection.activity.item

<br><br>



## templateItemTitleNext
