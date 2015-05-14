---
layout: page
title: Browser Support
group: "navigation"
---

In an ideal world we'd support the last two versions of the most used browsers. Unfortunatly this isn't always the case due to special requests.

Supporting legacy browsers can cause headaches when trying to use modern development techniques.

This page is a pool of useful scripts and code snippets that will help get around some of the issues we face.


# Index

* IE
    - Responsiveness
    - HTML5 Elements
* Testing
    - VirtualBox

---


## IE

### Responsiveness (IE6 - 8)
The [Respond](https://github.com/scottjehl/Respond) script provides support for browsers that don't support CSS3 Media Queries.

### HTML5 Elements (IE6 - 9)
The [HTML5Shiv](https://github.com/afarkas/html5shiv) script provides support for HTML5 elements that are not supported in legacy browsers.

## Testing

### VirtualBox (IE7+)
Download [VirtualBox](https://www.virtualbox.org/wiki/Downloads) to emulate different operating systems and the browsers they come with (Windows/IE).

You can find a snapshot of windows machines supporting IE6-11 [here](https://github.com/xdissent/ievms).

If you ever need to reinstall these machines (perhaps they've expired) you can use the node module [iectrl](https://www.npmjs.com/package/iectrl).