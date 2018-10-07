# Headless Browser
A headless browser is a web browser without a graphical user interface.

Headless browsers provide automated control of a web page in an environment similar to popular web browsers, but are executed via a command-line interface or using network communication.

They are particularly useful for testing web pages as they are able to render and understand HTML the same way a browser would, including execution of JavaScript and AJAX which are usually not available when using other testing methods.

## Headless browsers are used for:

- Test automation in modern web applications.
- Taking screenshots of web pages.
- Running automated tests for JavaScript libraries.
- Scraping web sites for data.
- Automating interaction of web pages.



# Browser controllers
- Those emulators aim to control the real browser.
- Simulate user interactions on browser and are able to retrieve actual information from current browser page.

### Advantage:
- Support for JS/AJAX interactions on page

### Disadvantage:
- Require the installed browser
- Need extra configuration
- Usually much slower than headless counterparts

### Examples:
### Headless mode
* [Google Chrome](https://blog.chromium.org/2017/05/chrome-59-beta-headless-chromium-native.html) - Headless mode is available  [on Linux and MacOS](https://chromium.googlesource.com/chromium/src/+/lkgr/headless/README.md#Usage-via-the-DevTools-remote-debugging-protocol) and Windows support came in Chrome 60.
* [Firefox](https://developer.mozilla.org/en-US/docs/Mozilla/Firefox/Headless_mode) – headless mode is available on linux, Windows and macOS since version 56, [usage](https://hacks.mozilla.org/2017/12/using-headless-mode-in-firefox/)

### As Service
* [Splash](https://scrapinghub.com/splash) – a headless web browser as service

### Scriptable
* [Navalia](https://github.com/joelgriffith/navalia) - Drive a headless browser with ease by using GraphQL
* [PhantomJS](http://phantomjs.org/) – a Scriptable Headless Browser using WebKit layout engine [development is suspended]
* [SlimerJS](https://slimerjs.org/) – a scriptable browser using Mozilla's Gecko layout engine.
* TrifleJS – a headless Internet Explorer scriptable browser using the Trident layout engine

### Testing
* [CasperJS](http://casperjs.org/) - Navigation scripting & testing utility for PhantomJS and SlimerJS [no longer actively maintained]
- [Selenium](https://github.com/SeleniumHQ/selenium): A browser automation testing framework and ecosystem. 
- [Sahi](http://sahipro.com/sahi-open-source/) - a cross-browser automation/testing tool with the facility to record and playback scripts.
- [TestCafe](https://github.com/DevExpress/testcafe) - A Node.js tool to automate end-to-end web testing. 

# Web Browser emulators
Simulates the behavior of a web browser, allowing you to make requests, click on links and submit forms programmatically.
* Pure HTTP browser emulators.
* Send a real HTTP requests against an application and parse the response content.

### Advantages:
* Simplicity to run and configure
* Speed
* Ability to run it without the need of a real browser

### Disadvantages:
* No JS/AJAX support

### Example:
* [Goutte](https://github.com/FriendsOfPHP/Goutte) - is a screen scraping and web crawling library for PHP.
* [Zombie.js](http://zombie.js.org/) – a simulated browser environment for Node.js. No browser required.
* [ENVJS](https://github.com/thatcher/env-js) – a simulated browser environment written in JavaScript for the Rhino engine.



# Browser engines
* [Blink](https://www.chromium.org/blink) (Google Chrome, Chromium, Opera and Vivaldi)
* [Gecko](https://developer.mozilla.org/en-US/docs/Mozilla/Gecko) (Firefox browser)
> * [Servo](https://servo.org/) (Experimental Browser Engine, by Mozilla Research)
* [Goanna](http://www.moonchildproductions.info/goanna.shtml) (fork of Mozilla's Gecko, used in the Pale Moon browser)
* [WebKit](https://webkit.org/) (Safari browser)

# JavaScript engines
* Google Chrome, the V8 engine (JavaScript, ECMA-262, edition 6)
> * V8 - open source, developed by Google, part of Google Chrome and Node.js
* Mozilla Firefox, the SpiderMonkey, and Rhino (JavaScript, ECMA-262, edition 6)
> * SpiderMonkey, the first JavaScript engine, which powered Netscape Navigator and today powers Firefox
> * Rhino, managed by the Mozilla Foundation, open source, developed entirely in Java
* Apple Safari, the Nitro engine (JavaScript, ECMA-262, edition 6)
> * JavaScriptCore - open source, marketed as Nitro and developed by Apple for Safari
* [Duktape](https://duktape.org/), an embeddable engine, with focus on portability and a compact footprint.
* JerryScript, is an ultra-lightweight JavaScript engine for the Internet of Things.
* Esper, a JavaScript self-interpreter with a focus on sandboxed execution and runtime introspection.


* https://en.wikipedia.org/wiki/Headless_browser

* [List of headless web browser](http://dhamaniasad.github.io/HeadlessBrowsers)
