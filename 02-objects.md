### Basic concepts
* An object is a compsite value: it aggregates multiple values and allows you to store and retrieve those valaues by name.
* Object is like hashtable, dictionary, associcative arrary
* Any value in JS that is **NOT** a string, a number, a boolean, null or undefined is an object
* A property has a name and a value. A property name may be anything, including empty string. The value of a property is called property attribute.
* The property name of an object must be unique.

### Object creation
* create via object literals: 
  ``` javascript
  var empty = {};
  var point = {x: 0, y: 0};
  var contact = {'first name': 'James', 'last name': 'Bond', 'age': 30, 'nationality': 'British'};
  ```
* create with **new**
  ``` javascript
  var o = new Object();
  var a = new Arrary();
  var d = new Date();
  var r = new RegExp('js');
  ```
 * Object.create()
 ``` javascript
 var o1 = Object.create({x: 1, y: 1});
 var o2 = Object.create(null);  // inherits no props or methods
 var o3 = Object.create(Object.prototype); // like {} or new Object(), it's an empty object
 ```

### Object and Instances
``` javascript
funciton Person(first, last) {
  this.first = first;
  this.last = last;
}

Person.prototype.fullName = function() {
  return this.first + ' ' + this.last;
}

p = new Person('Steve', 'Jobs');
console.log(p.fullName()); // Steve Jobs
console.log(typeof Person); // function
console.log(typeof p); // object
console.log(p instanceof Person); true
console.log(p.constructor.name); // Person
console.log(Person.name); // Person
```
