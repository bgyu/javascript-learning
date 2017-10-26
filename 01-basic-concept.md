# Types, Values and Variables

Two type categories in javascript:
## Primitive types:
   * numbers
   * strings
   * booleans
   * null
   * undefined
   
   Facts:
   1. Primitives are immutable
   2. Primitives are compared by **value**
   
## Object types: 
   ### Any Javascript value that is not a number, a string, a boolean, null or undefined (aka. Not primitive types) is an object
      
   #### Object definition: 
   ##### An object is a collection of properties where each property has a name and a value
   
      * normal object: key-value pairs, unordered collections, like dictinary in Python
      * array: ordered collections, like array in Python
      * function: a special object which has executable code associated with it

  #### Facts:
  1. Objects are mutable, their values can be changed
  2. Objects are compared by **reference**, two objects are only the same when they refer to the same underlying object
      
  ### Constructor:
  #### A function that is written to be used to initialize a newly created object via **new** operator
  ``` javascript
  function Rectangle(left, top, right, bottom) {
    this.left = left;
    this.top = top;
    this.right = right;
    this.bottom = bottom;
  }
  
  Rectangle.prototype.area = function() {
    const width = this.right - this.left;
    const height = this.bottom - this.top;
    return width * height;
  }
  
  var rect = new Rectangle(10, 20, 60, 70);
  console.log('The area of rectangle is ' + rect.area());
  // output: The area of rectangle is 2500
  ```
 
 # Important facts:
 * In JavaScript, null and undefined are the only values that methods cannot be invoked on
 * In JavaScript, strings are immutable
 * JavaScript variables are untyped: you can assign a value of any type to a variable, and you can later assign a value of a different type to the same variable. Variables are declared with the var keyword
 * JavaScript does not make a distinction between integer values and floating-point values. All numbers in JavaScript are represented as floating-point values. 
 
 
 #### Scope: 
 * Variables declared out- side of a function are global variables and are visible everywhere in a JavaScript program.    
 * Variables declared inside a function have function scope and are visible only to code that appears inside that function
 * Javascript is using **function scope**, which means variables winthin the function are visible anywhere in the function, not just the block they are defined.
 ``` javascript
var scope = "global"; 
function f() {
  console.log(scope); // Prints "undefined", not "global", because global scope variable becomes hidden due to same name local variable
  var scope = "local"; // Variable initialized here, but defined everywhere console.log(scope); // Prints "local"
}
```
The above code is equivalent to this:
``` javascript
var scope = "global";
function f() {
  var scope;  // will hide global scope
  console.log(scope);  // will print "undefined" because it is not initialized
  scope = "local";  // now scope is "local"
 }
 ```
 * Since javascript has a ***function scope***, it's a good practice to define all variables at the top of a function instead of the place they are used. This makes the program much clearer.
 
