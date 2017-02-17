#Front-end Job Interview Questions

This file contains a number of front-end interview questions that can be used when vetting potential candidates. It is by no means recommended to use every single question here on the same candidate (that would take hours). Choosing a few items from this list should help you vet the intended skills you require.

**Note:** Keep in mind that many of these questions are open-ended and could lead to interesting discussions that tell you more about the person's capabilities than a straight answer would.

## <a name='toc'>Table of Contents</a>

  1. [General Questions](#general)
  1. [HTML Questions](#html)
  1. [CSS Questions](#css)
  1. [JS Questions](#js)
  1. [jQuery Questions](#jquery)
  1. [Coding Questions](#jscode)
  1. [Fun Questions](#fun)

## <a name='toc'>Getting Involved</a>

  1. [Original Contributors](#contributors)
  1. [Recent Contributors](https://github.com/h5bp/Front-end-Developer-Interview-Questions/graphs/contributors)
  1. [How to Contribute](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/CONTRIBUTING.md)
  1. [License](https://github.com/h5bp/Front-end-Developer-Interview-Questions/blob/master/LICENSE.md)

####[[⬆]](#toc) <a name='general'>General Questions:</a>

* **What did you learn yesterday/this week?**
* **What excites or interests you about coding?**
  * How different languages differ in their implementation of functionality; uncovering quirks; the evolution of syntax as languages evolve.
* **What UI, Security, Performance, SEO, Maintainability or Technology considerations do you make while building a web application or site?**
  * UI: simplicity of design, legibility, minimalism
  * Security: Wordpress admin privileges, 2-factor authentication, never letting credit card information touch the server, OAuth - would like to learn more about this field
  * Performance: Google developer tools to assess latency, compressed stylesheets, initial loading of essential CSS styles, lazy-loading, targeted loading of retina images
  * SEO: descriptive titles, keywords in header tags and throughout body content, sitemaps, robots.txt
  * Maintainability: organized code, file naming conventions, bower 3rd party library management, unit testing
  * Technology: data limitations on mobile browsers, compatibility across devices, Wordpress for admin management
* **Talk about your preferred development environment. (OS, Editor or IDE, Browsers, Tools, etc.)**
  * I work both on Mac and Windows. I have experience using Linux in the past, but not in depth.
  * Editor: Atom & Sublime Text
  * IDE/Browser/Tools: Codekit on my Mac for pre-processing and browser refreshing. MAMP for the local server. On Windows I use WAMP paired with Prepos. Familiar with Xcode and Netbeans for C and Java compiling.
* **What is version control and which system are you most familiar with?**
  * Git
  * Version control is a method of keeping track of changes to a file (or set of files). It allows you to revert to previous states, record modifications and recover from issues, should they arise.
  * The most basic form of a VCS is to locally copy file directories, labeling with a timestamp, as a project progresses. This is often error prone and difficult to maintain.
  * To deal with this, programmers created the first iteration of VCSs using local databases that kept track of revisions. Today, the Mac OS developer tools come preinstalled with one variation of this VCS called RCS. It works by keeping patch sets that contain the differences between files.
  * The next iteration of VCSs were Centralized Version Control Systems (CVCSs), which employ a central server and allow for collaboration between multiple developers. Examples of CVCSs include CVS, Subversion, and Perforce. All enable developers to check out files from a central repository and are easier to administer than databases of changes stored locally on each machine. Both CVCSs and local VCSs run the risk of total data loss should either point of storage fail.
  * Distributed Version Control Systems (DVCSs) safeguard against file loss by cloning repositories in their entirety to each client. This means that if any server dies, any of the client repositories can be copied back up to restore the data. Examples of DVCSs include Git, Mercurial, Bazaar and Darcs.
* **Can you describe your workflow when you create a web page?**
  * Planning: Discussion with client, acknowledgement of contract, background research, questions like "what are the existing assets, media, color schemes, logos, styles, fonts etc.?" - "what are your top 3 goals?" - "who will be maintaining the site?"
  * Mock-ups: wireframing (Axure), mock designs (Photoshop, Illustrator), flow diagrams
  * Iterations: revisions with client, testing in browser, "is site satisfying goals?", sign off by client
  * Building: translating finalized mock designs into responsive html/css/javascript, creation of back-end databases or server side code, intermediary sign offs by client if needed
  * The Final Nod: launch site, push assets live, provide client with agreed upon resources
* **If you have 5 different stylesheets, how would you best integrate them into the site?**
  * If they were project specific stylesheets, I would @import each as SASS files into the primary stylesheet. Main goal here would be to limit the number of separate HTTP requests that occur do to multiple `<link rel="stylesheet">` in the `<head>`.
  * If they were vendor stylesheets, I would make sure to minify all CSS, combining them into one file if appropriate.
* **Can you describe the difference between progressive enhancement and graceful degradation?**
  * Progressive enhancement: start with a basic design and progressively enhance or add features for browsers that support them. This method is aligned with iterative design methods such as Agile.
  * Graceful degradation: provide a fall-back for older browsers so that they can still display important content within a more basic UI.
* **How would you optimize a website's assets/resources?**
  * Decrease the number and size of files that are downloaded by compressing images, minifying source code, combining files or streamlining markup.
  * Modernize: replace old technologies that load slowly, like iFrames or flash.
  * Make as few HTTP requests as possible.
  * Place Javascript `<script>` calls at the bottom of the page.
  * Use SVG instead of PNG files.
  * Investigate caching options.
* **How many resources will a browser download from a given domain at a time?**
  * Typically 6-8, depending on the browser
* **What are the exceptions?**
  * We can use subdomains pointing to the same domain to increase the concurrency of our downloads.
* **Name 3 ways to decrease page load (perceived or actual load time).**
  * Add a pre-loader graphic or other visual feedback so that the user is aware of loading progress
  * Load key CSS for "above-the-fold" elements as inline styles at the top of the page
  * Use lazy-loading of images to reduce the number of elements to load
* **If you jumped on a project and they used tabs and you used spaces, what would you do?**
  * I would switch to tabs as that is the convention for the project. I would also look into configuring my text editor to help me adhere to this convention.
* **Write a simple slideshow page**

  ```html
  <div class="slide"><img src="http://placehold.it/350x150"></div>
  <div class="slide"><img src="http://placehold.it/350x150"></div>
  <div class="slide"><img src="http://placehold.it/350x150"></div>
  ```

  ```css
  .slide img {
    width: 100%;
    height: 100%;
  }
  ```

  ```javascript
  (function slideshow(i) {

    var index = i;
    var slides = document.getElementsByClassName('slide');
    for (var i = 0; i < slides.length; i++) {
      slides[i].style.display = "none";
    }
    index++;
    if (index > slides.length) {index = 1;}
    slides[index - 1].style.display = "block";
    setTimeout(slideshow,2000,index);
  })(0);
  ```
* **What tools do you use to test your code's performance?**
  * Google PageSpeed Tools, Chrome Developer Tools
* **If you could master one technology this year, what would it be?**
  * React & Redux
* **What are the differences between Long-Polling, Websockets and SSE?**
  * These are different ways of requesting and receiving information from the server by the client.
  * Long-Polling: Server waits until there is new information available before resending to the client. The client then resends the request and the process begins again.
  * SSE (Server Sent Events): A connection is opened to allow the server to continually send new information to the client without needing to receive a new request every time.
  * Websockets: A connection is opened to allow the server and client to communicate continually, for real-time two-way traffic.
* **Explain the importance of standards and standards bodies.**
  * Standards enable us to write code that is guaranteed to work across platforms and browsers. Without standards we cannot be confident in the consistency and stability of our code as technologies evolve.
* **What is Flash of Unstyled Content? How do you avoid FOUC?**
  * FOUC occurs on page load when the browser tries to render elements for which it has yet to load styles. This can happen when styles are placed lower down on the page or when CSS rendering is dependent on asynchronous scripts.
  * To avoid FOUC CSS should be placed in the head of the page. Key styles should not be loaded using scripts.
* **Do your best to describe the process from the time you type in a website's URL to it finishing loading on your screen.**
  * The URL is translated to an IP Address through a series of progressive checks and queries. First the browser checks its local cache, then the OS cache, then the router cache, then the ISP cache and then finally, if it still hasn't found the IP address, it will look out through top-level nameservers until it hits the nameserver associated with the domain.
  * The IP address is used to open a TCP connection over which an HTTP request is sent.
  * The server responds to the HTTP request and passes requested data back to client browser (assuming status code 200).
  * The browser parses the response according to HTTP headers, rendering HTML on the screen.
* **Explain what ARIA and screenreaders are, and how to make a website accessible.**
  * ARIA is a set of ways to make web content accessible to people with disabilities. By adding alt tags to images and icons we allow someone who is blind to have visual content translated into speech.
* **Explain some of the pros and cons for CSS animations versus JavaScript animations**
  * CSS animations leverage the browser's graphic engine (and thus are less CPU-intensive) but are less flexible in terms of design and logic. May also not be supported in some browsers.
  * Javascript animations are CPU-intensive but offer you precise control over behavior and design.
* **Explain the following request and response headers:**
  * Difference between Expires, Date, Age and If-Modified: Expires - when does response become "stale". Date - when was response sent. Age - how long as object been in the cache. If-Modified-Since: returns a *304 Not Modified* if content is unchanged since a certain date.
  * DNT: Requests that a web application disable their tracking of a user.
  * Cache-Control: Instructs the browser or proxy whether or not to store content or whether to check cache content with the server before using it.
  * Transfer-Encoding: What type of encoding was used to transfer the data to the user (current methods include: chunked, compress, deflate, gzip and identity).
  * ETag: An identifier for a specific version of a resource, for example a message digest
* **What does CORS stand for and what issue does it address?**
  * CORS stands for Cross-Origin Resource Sharing. It is a W3C spec that enables resources to be loaded from a domain that is different than domain from which the requesting content is being served. The HTTP header Origin is checked by the server and it will either allow or disallow the request, sending back a response with Access-Control-Allow-Origin set to the request's origin. The browser then checks to see if Origin matches Access-Control-Allow-Origin.
  * CORS enables popular web functionality including API calls and web fonts.

####[[⬆]](#toc) <a name='html'>HTML Questions:</a>

* **What does a `doctype` do?**
  * The `doctype` declaration is a required preamble that is placed at the very top of all pages to tell the browser what version of html is being written. The current recommendation is to use `<!doctype html>`, which signifies that the document is using future-safe standards mode. Leaving it out may cause browsers to use older rendering specs, producing unwanted results.
* **What's the difference between standards mode and quirks mode?**
  * The `doctype` definition was originally intended for markup validators, but it was adopted as a way to identify legacy code that would be incompatible with modern CSS rendering. The browser chooses a rendering via doctype sniffing; if it finds that the document is modern, it renders in standards mode. Otherwise it will render in quirks mode, which has a better chance of being compatible with legacy code.
* **What are the limitations when serving XHTML pages?**

* **Are there any problems with serving pages as `application/xhtml+xml`?**
* **How do you serve a page with content in multiple languages?**
* **What kind of things must you be wary of when design or developing for multilingual sites?**
* **What are `data-` attributes good for?**
* **Consider HTML5 as an open web platform. What are the building blocks of HTML5?**
* **Describe the difference between cookies, sessionStorage and localStorage.**
* **Can you explain the difference between `GET` and `POST`?**
* **Describe the difference between `<script>`, `<script async>` & `<script defer>`.**

####[[⬆]](#toc) <a name='css'>CSS Questions:</a>
* What is the difference between classes and ID's in CSS?
* Describe what a "reset" CSS file does and how it's useful.
* Describe Floats and how they work.
* Describe z-index and how stacking context is formed.
* What are the various clearing techniques and which is appropriate for what context?
* Explain CSS sprites, and how you would implement them on a page or site.
* What are your favourite image replacement techniques and which do you use when?
* CSS property hacks, conditionally included .css files, or... something else?
* How do you serve your pages for feature-constrained browsers?
  * What techniques/processes do you use?
* What are the different ways to visually hide content (and make it available only for screen readers)?
* Have you ever used a grid system, and if so, what do you prefer?
* Have you used or implemented media queries or mobile specific layouts/CSS?
* Any familiarity with styling SVG?
* How do you optimize your webpages for print?
* What are some of the "gotchas" for writing efficient CSS?
* What are the advantages/disadvantages of using CSS preprocessors? (Sass, Compass, Stylus, LESS)
  * If so, describe what you like and dislike about the CSS preprocessors you have used.
* How would you implement a web design comp that uses non-standard fonts?
* Explain how a browser determines what elements match a CSS selector.
* Explain your understanding of the box model and how you would tell the browser in CSS to render your layout in different box models.
* What does ```* { box-sizing: border-box; }``` do? What are its advantages?
* List as many values for the display property that you can remember.
* What's the difference between inline and inline-block?
* What's the difference between a relative, fixed, absolute and statically positioned element?
* The 'C' in CSS stands for Cascading.  How is priority determined in assigning styles (a few examples)?  How can you use this system to your advantage?
* What existing CSS frameworks have you used locally, or in production? (Bootstrap, PureCSS, Foundation etc.)
  * If so, which ones? If you could, how would you change/improve them?
* Have you played around with the new CSS Flexbox or Grid specs?
* How is responsive design different from adaptive design?
* Have you ever worked with retina graphics? If so, when and what techniques did you use?

####[[⬆]](#toc) <a name='js'>JS Questions:</a>

* **Explain event delegation**
* **Explain how `this` works in JavaScript**
* **Explain how prototypal inheritance works**
* **How do you go about testing your JavaScript?**
  * The two main testing methodologies are Test-Driven Development (TDD) and Behavior-Driven Development (BDD). The main difference being in the languages used to make testable assertions. I have experience with BDD unit testing (ex: `expect(x).toEqual(y)`) using Mocha (provide test structure), Karma (run tests and display results) and Chai (make assertions).
  * There are a number of different types of tests:
    * Unit Tests: Small, test a specific chunk of code.
    * Integration Tests: Ensure that separate parts of your application work in tandem.
    * Acceptance Tests: Showcase required functionality for management or stake holders.
    * Regression Tests: The process of re-running unit tests after making any necessary changes to fix failing integration tests.
* **AMD vs. CommonJS?**
  * AMD and CommonJS are the two most prevalent JavaScript loaders. Their purpose is to help organize our applications' business logic, loading modules of code either asynchronously (AMD) or synchronously (CommonJS) in a more performant manner.
  * Recently, CommonJS has been implemented by Node.js on the server (using `require` and `module.exports`) and webpack and browserify client-side. Meanwhile, AMD's async callback-style loading is seen in require.js and Dojo.
  * Happily, ES6 brings us native support for both synchronous and asynchronous modules using the `import` and `export` keywords.
  * The purpose of modularizing your JavaScript code (and rise in popularity of these loader technologies) stems from the increasing difficulty in managing namespaces with 3rd-party dependencies. There is also a need to control when dependencies are in the load chain.
* **Explain why the following doesn't work as an IIFE and what needs to be changed to make it function as desired:** `function foo(){ }();`.
* **What's the difference between a variable that is: `null`, `undefined` or `undeclared`?**
* **How would you go about checking for any of these states?**
* **What is a closure, and how/why would you use one?**
* **What's a typical use case for anonymous functions?**
* **How do you organize your code? (module pattern, classical inheritance?)**
* **What's the difference between host objects and native objects?**
* **Difference between: `function Person(){}`, `var person = Person()`, and `var person = new Person()`?**
* **What's the difference between `.call` and `.apply`?**
* **Explain `Function.prototype.bind`.**
* **When do you optimize your code?**
* **When would you use `document.write()`?**
* **What's the difference between feature detection, feature inference, and using the UA string.**
* **Explain AJAX in as much detail as possible.**
* **Explain how JSONP works (and how it's not really AJAX).
* Have you ever used JavaScript templating? If so, which libraries?**
* **Explain "hoisting".**
* **Describe event bubbling.**
* **What's the difference between an "attribute" and a "property"?**
* **Why is extending built in JavaScript objects not a good idea?**
* **Difference between document load event and document ready event?**
* **What is the difference between `==` and `===`? Give an example.**
  * Double equals performs type conversion between operands before checking their values for equality, whereas triple equals does not. Explicitly stated, in order for two operands to be triple equal they must be both equal in value and the same types.
  ```javascript
  123 == '123' // true
  123 === '123' // false
  ```
* **Explain the same-origin policy with regards to JavaScript.**
* **Make this work:**
```javascript
duplicate([1,2,3,4,5]); // [1,2,3,4,5,1,2,3,4,5]
```
* **Why is it called a Ternary expression, what does the word "Ternary" indicate?**
  * A ternary expression is a 3-part statement that checks a condition and executes accordingly. Ternary is a word that comes from the n-ary word setup (along with unary and binary); the prefix of each of these n-ary words represents how many inputs the operand accepts- here, it's 3.
  * A ternary operand (?) accepts three parameters: the condition, the action to be taken if true and action to be taken if false. For example:
  ```javascript
  if (starwars === 'the best') ? return 'yes, I agree' : return 'WHAT?!';
  ```
* **What is `"use strict";`? What are the advantages and disadvantages to using it?**
  * This is a special mode that we can chose to handle our JS code at runtime. `"use strict"` enforces more rigorous code standards by making otherwise silent errors throw exceptions and by preventing certain actions. It can be applied to a whole file by placing the string at the top of a file or it can be used only in certain functions.
  * Advantages: `"use strict"` will help pinpoint errors in buggy code, flag unsafe actions and restrict usage of unstable features. It will also prevent global variable leakage because the compiler will no longer create a variable when it comes to assign a value to an identifier that has not been declared. For example:
  ```javascript
  function baz(foo) {
    foo = "bar";
    bam = "yay";
  }
  ```
  In strict mode, the compiler will throw an error instead of silently creating a global variable when it hits the assignment `bam = "yay"`. 
  * Disadvantages: It may cause compatibility issues in older browsers and will be difficult to integrate into existing code. When using global strict mode, you cannot concatenate scripts that are not using `"use strict"`.
* **Create a for loop that iterates up to `100` while outputting "fizz" at multiples of `3`, `"buzz"` at multiples of `5` and "fizzbuzz" at multiples of `3` and `5`.**
* **Why is it, in general, a good idea to leave the global scope of a website as-is and never touch it?**
* **Describe inheritance and the prototype chain in JavaScript and give an example (Source: [TopTal Hiring Guide](https://www.toptal.com/javascript#hiring-guide))**
  * Inheritance in JavaScript is made possible because objects reference other objects called prototypes. When a reference is made to a property that an object does not itself contain, its prototype is checked. If the first prototype also does not contain this property, its prototype is checked. This process repeats until the end of the "prototype chain" is reached, upon which the property is set as undefined.
  ```
  function Person() { this.species = "human" };

  function Child() { this.age = "young" };
  Child.prototype = new Person();

  function Adult() { this.age = "mature" };
  Adult.prototype = new Person();

  var sally = new Child();
  var fred = new Adult();

  console.log(sally.species); // "human"
  console.log(fred.age); // "mature"
  ```

* **Compare and contrast objects and hashtables in JavaScript (Source: [TopTal Hiring Guide](https://www.toptal.com/javascript#hiring-guide))**
  * In JavaScript, objects are essentially hashtables consisting of key-value pairs. Keys must be strings or will be converted to strings automatically.

* **Consider the code snippet below. What will the alert display? (Source: [TopTal Hiring Guide](https://www.toptal.com/javascript#hiring-guide))**
```javascript
var foo = new Object();
var bar = new Object();
var map = new Object();

map[foo] = "foo";
map[bar] = "bar";

alert(map[foo]);
```
  * In JavaScript, object keys must be strings and will be silently converted into a string if otherwise. When we set `map[foo] = "foo"`, since `foo` is an empty object and not a string, it is converted into a string using its `.toString()` method. Neither `foo` nor `bar` have custom `.toString()` methods so the default Object method is used. By default, `Object.toString() = "[Object object]"` and so we are essentially setting:
  ```
  map["[Object object]"] = "foo";
  map["[Object object]"] = "bar";
  ```
  Now it is clear that we are overwriting the same key with a new value, `bar`. And hence `alert(map[foo]) = alert(["[Object object]"]) = "bar"`.
* **What is the significance of, and reason for, wrapping the entire content of a JavaScript source file in a function block? (Source: [TopTal Hiring Guide](https://www.toptal.com/javascript#hiring-guide))**
    * Wrapping an entire source file encapsulates variables and preserves the namespace by preventing name conflicts with any other modules or libraries.
    * This technique also allows us to use aliases for global variables. For example we can enable the use of jQuery's `$` reference by passing in the `jQuery` variable to the IIFE as follows:

    ```javascript
    (function($){ })(jQuery);
    ```
* **What is an n-ary operator? What are the three main operators in JS? Give examples of each.**
  * n-ary operators accept a certain number of inputs based on their prefix, ranging from unary (1 input), to binary (2 inputs), to ternary (3 inputs).
  * Unary operators: unary plus/minus (`+`/`-`) as in `-1`
  * Binary operators: multiplication operator, the addition operator, the division operator as in `2 + 3`
  * Ternary operators: `?:` as in `conditional ? truthy_block : falsey_block`

####[[⬆]](#toc) <a name='jquery'>jQuery Questions:</a>

* Explain "chaining".
* Explain "deferreds".
* What are some jQuery specific optimizations you can implement?
* What does `.end()` do?
* Name 4 different values you can pass to the jQuery method.
  * Selector (string), HTML (string), Callback (function), HTML element, object, array, element array, jQuery Object, etc.
* What is the difference between `.get()`, `[]`, and `.eq()`?

####[[⬆]](#toc) <a name='jscode'>Code Questions:</a>

*Question: How would you make this work?*
```javascript
add(2, 5); // 7
add(2)(5); // 7
```

*Question: What value is returned from the following statement?*
```javascript
"i'm a lasagne hog".split("").reverse().join("");
```

*Question: What is the value of `window.foo`?*
```javascript
( window.foo || ( window.foo = "bar" ) );
```

*Question: What is the outcome of the two alerts below?*
```javascript
var foo = "Hello";
(function() {
  var bar = " World";
  alert(foo + bar);
})();
alert(foo + bar);
```

*Question: What is the value of `foo.length`?*
```javascript
var foo = [];
foo.push(1);
foo.push(2);
```

####[[⬆]](#toc) <a name='fun'>Fun Questions:</a>

* What's a cool project the you've recently worked on?
* What are some things you like about the developer tools you use?
* Do you have any pet projects? What kind?
* What's your favorite feature of Internet Explorer?
* How do you like your Coffee?


####[[⬆]](#toc) <a name='contributors'>Original Contributors:</a>

The majority of the questions were plucked from an [oksoclap](http://oksoclap.com/) thread created **originally** by [Paul Irish](http://paulirish.com) ([@paul_irish](http://twitter.com/paul_irish)) and collectively contributed to by the following: [@bentruyman](http://twitter.com/bentruyman) [@cowboy](http://twitter.com/cowboy) [@ajpiano](http://ajpiano)  [@SlexAxton](http://twitter.com/slexaxton) [@boazsender](http://twitter.com/boazsender) [@miketaylr](http://twitter.com/miketaylr) [@vladikoff](http://twitter.com/vladikoff) [@gf3](http://twitter.com/gf3) [@jon_neal](http://twitter.com/jon_neal) [@sambreed](http://twitter.com/sambreed) [@iansym](http://twitter.com/iansym)
