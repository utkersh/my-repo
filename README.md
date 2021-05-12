# DOM(Document Object Model)
The *Document Object Model(DOM)* is a programming interface for [HTML](https://www.google.com) and [XML](https://www.google.com) documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.
A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

# How does it helps?
The *Document Object Model (DOM)* is an application programming interface (API) for HTML and XML documents. It defines the logical structure of documents and the way a document is accessed and manipulated. In the DOM specification, the term "document" is used in the broad sense - increasingly, XML is being used as a way of representing many different kinds of information that may be stored in diverse systems, and much of this would traditionally be seen as data rather than as documents. Nevertheless, XML presents this data as documents, and the DOM may be used to manage this data.

# How to access it?
To begin using DOM we don't have to do anything special. Different browsers have different implementations of the DOM, and these implementations exhibit varying degrees of conformance to the actual DOM standard (a subject we try to avoid in this documentation), but every web browser uses some document object model to make web pages accessible via JavaScript.
When you create a script–whether it's inline in a `<script>` element or included in the web page by means of a script loading instruction–you can immediately begin using the API for the [`document`](https://www.google.com) or [`window`](https://www.google.com) elements to manipulate the document itself or to get at the children of that document, which are the various elements in the web page. Your DOM programming may be something as simple as the following, which displays an [`alert`](https://www.google.com) message by using the alert() function from the window object, or it may use more sophisticated DOM methods to actually create new content, as in the longer example below.
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

# What are JS helper method?

Helper methods gained huge popularity in a very short period of time after the [ES6](https://www.google.com) was introduced. Some of these helper methods already existed in some external libraries, and developers really wanted them to be native to JavaScript itself. Using helpers have many benefits like making the code more readable, reducing the number of lines of code, etc.

 #  Some of the helper methods are:
   
__1.every() Method:__ his method is used to check if all elements of an array pass the test that is implemented by the passed higher-order function. What compiler does under the hood is, it iterates over the employees array and check for all employee, if he is a developer or not. As in this case, it should return false.
```javascript
const employees = [
  { name: "Sam",      age: 25, role: "Developer" },
  { name: "John",     age: 32, role: "Manager"   },
  { name: "Ronaldo",  age: 29, role: "Architect" },
  { name: "Perker",   age: 25, role: "Developer" },
  { name: "Sophia",   age: 38, role: "Director"  },
  { name: "kristine", age: 21, role: "Developer" },
];
  
function isDeveloper(employee) {
  return employee.role === "Developer";
}
console.log(employees.every(isDeveloper));
```
__Output:__
```
False
```
__2.fill() Method:__ This method fills the array with a static value. It overrides all array values starting from the first element(0th index) and up to the last element(array.length-1 index).
```javascript
const employees = [
    { name: "Sam",      age: 25, role: "Developer" },
    { name: "John",     age: 32, role: "Manager"   },
    { name: "Ronaldo",  age: 29, role: "Architect" },
    { name: "Perker",   age: 25, role: "Developer" },
    { name: "Sophia",   age: 38, role: "Director"  },
    { name: "kristine", age: 21, role: "Developer" },
];
          
const newEmployees = employees.fill(
    { name: "Sam", age: 25, role: "Developer" });
console.log(employees);
  
console.log(newEmployees === employees);
```
__Output:__
```
[
 { name: 'Sam', age: 25, role: 'Developer' },
 { name: 'Sam', age: 25, role: 'Developer' },
 { name: 'Sam', age: 25, role: 'Developer' },
 { name: 'Sam', age: 25, role: 'Developer' },
 { name: 'Sam', age: 25, role: 'Developer' },
 { name: 'Sam', age: 25, role: 'Developer' }
]

true
```
__3.filter() Method:__ This method filters the array that passes the test with the function passed to it.

```
javascript
const employees = [
    { name: "Sam",      age: 25, role: "Developer" },
    { name: "John",     age: 32, role: "Manager"   },
    { name: "Ronaldo",  age: 29, role: "Architect" },
    { name: "Perker",   age: 25, role: "Developer" },
    { name: "Sophia",   age: 38, role: "Director"  },
    { name: "kristine", age: 21, role: "Developer" },
];
          
function filterDevEmp(employee) {
  return employee.role === "Developer";
}
const filteredDevEmployees = employees.filter(filterDevEmp);
console.log(filteredDevEmployees);
```
__Output:__
```
[
 { name: 'Sam', age: 25, role: 'Developer' },
 { name: 'Perker', age: 25, role: 'Developer' },
 { name: 'kristine', age: 21, role: 'Developer' }
]
```
