# DOM(Document Object Model)
The *Document Object Model(DOM)* is a programming interface for [HTML](https://www.google.com) and [XML](https://www.google.com) documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.
A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

# How does it help?
The *Document Object Model (DOM)* is an application programming interface (API) for HTML and XML documents. It defines the logical structure of documents and the way a document is accessed and manipulated. In the DOM specification, the term "document" is used in the broad sense - increasingly, XML is being used as a way of representing many different kinds of information that may be stored in diverse systems, and much of this would traditionally be seen as data rather than as documents. Nevertheless, XML presents this data as documents, and the DOM may be used to manage this data.

# How to access it?
To begin using DOM we don't have to do anything special. Different browsers have different implementations of the DOM, and these implementations exhibit varying degrees of conformance to the actual DOM standard (a subject we try to avoid in this documentation), but every web browser uses some document object model to make web pages accessible via JavaScript.
When you create a script–whether it's inline in a `<script>` element or included in the web page using a script loading instruction–you can immediately begin using the API for the [`document`](https://www.google.com) or [`window`](https://www.google.com) elements to manipulate the document itself or to get at the children of that document, which are the various elements in the web page. Your DOM programming may be something as simple as the following, which displays an [`alert`](https://www.google.com) message by using the alert() function from the window object, or it may use more sophisticated DOM methods to create new content, as in the longer example below.
 This JS code will display an alert when the document is loaded
 ```javascript
 <body onload="window.alert('Welcome to my home page!');">
 ```
Another example. this function creates anew H1 element, adds text to that element, and then adds the `H1` to the tree for this document:
```HTML
<html>
  <head>
    <script>
       // run this function when the document is loaded
       window.onload = function() {

         // create a couple of elements in an otherwise empty HTML page
         const heading = document.createElement("h1");
         const heading_text = document.createTextNode("Big Head!");
         heading.appendChild(heading_text);
         document.body.appendChild(heading);
      }
    </script>
  </head>
  <body>
  </body>
</html>
```

# What are the DOM helper method?

The Document object represents the root node of the HTML document. The nodes are organized in a tree structure, called the DOM tree. Objects in the DOM tree may be addressed and manipulated by using methods on the objects. 

 #  Some of the helper methods are:
   
__1. elementIndex:__ 
```javascript
export function elementIndex(el) {
    var index = 0;
    while ((el = el.previousElementSibling)) {
        index++;
    }
    return index;
}
```

__2. indexInParent:__ 
```javascript
export function indexInParent(el) {
    let children = el.parentNode.childNodes;
    let num = 0;

    for (let i = 0; i < children.length; i++) {
        if (children[i] == el) return num;
        if (children[i].nodeType == 1) num++;
    }
    return -1;
}
```

__3. indexOfParent:__ 

```javascript
export function indexOfParent(el) {
    return [].indexOf.call(el.parentElement.children, el);
}
```
__4. matches:__

```javascript
export function matches(elem, selector) {
    const isMsMatch = 'msMatchesSelector' in elem && elem.msMatchesSelector(selector);
    const isMatchSelector = 'matchesSelector' in elem && elem.matchesSelector(selector)
    const isMatch = 'matches' in elem && elem.matches(selector);
    return isMsMatch || isMatchSelector || isMatch;
    // Return the result of the test
    // If any of the above variables is true, the return value will be true
}
```
__5. closest:__

```javascript
export function getClosest(elem, selector) {
    // This allows for matching based on any selector, not just a single class.
    for (; elem && elem !== document; elem = elem.parentNode) {
        // Traverse up the dom until document is reached
        if (matches(elem, selector)) {
            // Test each element to see if it matches. If it does, return it.
            return elem
        }
    }
    return null;
}

export const closest = getClosest;
```
__6. offset top:__

```javascript
export function getOffsetTop(el) {
    let offsetTop = 0;
    do {
        if (!isNaN(el.offsetTop)) {
            offsetTop += el.offsetTop;
        }
    } while (el = el.offsetParent);
    return offsetTop;
}
```
__7. next:__ Get the immediately following sibling of each element in the set of matched elements.



```javascript
export function next(elem, selector) {
    if (elem.nextElementSibling) {
        if (matches(elem.nextElementSibling, selector)) {
            return elem.nextElementSibling;
        } else {
            return prev(elem.nextElementSibling, selector);
        }
    }

    return false;
}
```
# Thank You
