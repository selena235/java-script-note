# java-script-note
# java script

```jsx
//var
let a;
let name = "Simon";
console.log(name);
//fuction
function foo(x, condition) {
  if (condition) {
    console.log(x);
    const x = 2;
    console.log(x);
  }
}
//if else 
let name = "kittens";
if (name === "puppies") {
  name += " woof";
} else if (name === "kittens") {
  name += " meow";
} else {
  name += "!";
}
name === "kittens meow";
//while
while (true) {
  // an infinite loop!
}
//do while
let input;
do {
  input = get_input();
} while (inputIsNotValid(input));

//for loop
for (let i = 0; i < 5; i++) {
  // Will execute 5 times
}
//switch
switch (action) {
  case "draw":
    drawIt();
    break;
  case "eat":
    eatIt();
    break;
  default:
    doNothing();
}
//const object
const obj = {
  name: "Carrot",
  for: "Max",
  details: {
    color: "orange",
    size: 12,
  },
};

<button onclick="document.getElementById('demo').innerHTML = Date()">The time is?</button>

```

var, datatype, data structure , control flow, loop(do while, for loop),function, events,let,const,var

difference b/n let, const, var

**var is function-scoped while let and const are block-scoped.** var variables can be reassigned while let and const variables can not. block-scoped is the can not be if it’s outside the block or function

let is a keyword in JavaScript that allows you to declare a block-scoped variable. This means that the variable is only accessible within the block of code in which it is declared, and not outside of that block

 var is a keyword in JavaScript that allows you to declare a variable with either function scope or global scope. 

const is a keyword in JavaScript that allows you to declare a variable with block scope that cannot be reassigned. This means that the variable is only accessible within the block of code in which it is declared, and its value cannot be changed once it has been assigned.

function-the most important java script with a return type

datatype-variable definition

data structure-is ****a format to organize, manage and store data
 in a way that allows efficient access and modification. arrays and object are most known data structure 
.

```
//data structure
// A collection of the values 1, 2 and 3
const arr = [1, 2, 3]

// Each value is related to one another, in the sense that each is indexed in a position of the array
const indexOfTwo = arr.indexOf(2)
console.log(arr[indexOfTwo-1]) // 1
console.log(arr[indexOfTwo+1]) // 3

// We can perform many operations on the array, like pushing new values into it
arr.push(4)
console.log(arr) // [1,2,3,4]
```

A**rray-** is a collection of items stored at contiguous memory locations.

```
const arr = ['a', 'b', 'c', 'd']
console.log(arr[2]) // c
```

an **object-** is a collection of **key-value pairs**. This data structure is also called map, dictionary
 or hash-table ****in other programming languages. objects in JavaScript do not have fixed shapes properties can be added, deleted, re-ordered, mutated, or dynamically queried at any time.

```
const obj = {
    prop1: "I'm",
    prop2: "an",
    prop3: "object"
}
```

control flow state-occurring condition   

      if else-is used to execute a block of code only if the specified condition evaluates to true. if not true uses the other block

`if (new Date().getHours() < 18) {
document.getElementById("demo").innerHTML = "Good day!";
}else{`

`document.getElementById("demo").innerHTML = "Good night!";`

`}`

      switch-tests a variable or expression against a series of values until it finds a match

`let day;
switch (new Date().getDay()) {
case 0:
day = "Sunday";
break;
case 1:
day = "Monday";
break;
case 2:
day = "Tuesday";
break;
case 3:
day = "Wednesday";
break;
case 4:
day = "Thursday";
break;
case 5:
day = "Friday";
break;
case  6:
day = "Saturday";
}
document.getElementById("demo").innerHTML = "Today is " + day;`

loop-if you want to run the same code over and over again, each time with a different value.

     for loop-incrementing and decrementing variable  iterating 

`<script>
const cars = ["BMW", "Volvo", "Saab", "Ford", "Fiat", "Audi"];`

`let text = "";
for (let i = 0; i < cars.length; i++) {
text += cars[i] + "<br>";
}`

`document.getElementById("demo").innerHTML = text;
</script>`

     do while loop is a variant of the while loop, which evaluates the condition at the end of each loop iteration.

```jsx
var i = 1;
do {
    document.write("<p>The number is " + i + "</p>");
    i++;
}
while(i <= 5);
```

events- can be something the browser does, or something a user does. on click is the event in the js. 

```jsx
<button onclick="document.getElementById('demo').innerHTML = Date()">The time is?</button>
```

# JSON

**J**ava**S**cript **O**bject **N**otation- **text format** for storing and transporting data. JSON makes it possible to store JavaScript objects as text.

JSON syntax is derived from JavaScript object notation syntax:

- Data is in name/value pairs
- Data is separated by commas
- Curly braces hold objects
- Square brackets hold arrays

---

# JSON Values

In **JSON**, *values* must be one of the following data types:

- a string
- a number
- an object
- an array
- a boolean
- null

In **JavaScript** values can be all of the above, plus any other valid JavaScript expression, including:

- a function
- a date
- undefined
- {"name":"John"} string should be in a double quote

# Parsing Functions

Functions are not allowed in JSON. If you need to include a function, write it as a string. You can convert it back into a function later:

```jsx
<script>
const text = '{"name":"John", "age":"function() {return 30;}", "city":"New York"}';
const obj = JSON.parse(text);
obj.age = eval("(" + obj.age + ")");
document.getElementById("demo").innerHTML = obj.name + ", " + obj.age(); 
</script>
```

JSON. parse ():

```jsx
var json='{"book":{"name":"harrypotter","author":"rowling",
"charcters":["harry potter","ron weki"]  }}';
var obj=JSON.parse(json);
```

**JSON. stringify():**

exchange data to/from a web server. Convert a JavaScript object into a string

JSON string from java script object

```jsx
<script>
const obj = {name: "John", age: 30, city: "New York"};
const myJSON = JSON.stringify(obj);
document.getElementById("demo").innerHTML = myJSON;
</script>
```

**JSON object**

You can create a JavaScript object from a JSON object literal:

```jsx
<script>
const myObj = {"name":"John", "age":30, "car":null};
document.getElementById("demo").innerHTML = myObj.name;
</script>
```

**Looping an Object**

```jsx
<script>
const myJSON = '{"name":"John", "age":30, "car":null}';
const myObj = JSON.parse(myJSON);

let text = "";
for (const x in myObj) {
  text += x + ", ";
}
document.getElementById("demo").innerHTML = text;
</script>
```

# DOM(document object model)

```jsx
<html>
<head>
</head>
<body>
<h1>
<div id="div1">
<p>p tag 1</p>
</div>
<div id="div2">
<p>tag2</p>
</div>
</body>
</html>

```

![ok.PNG](JSON%207e4b260973454fed93b284e912c2ad4b/ok.png)

head is element node 

my title is text node(not an object)

id=”div1” is attribute node corresponds to id and js can add by it effect and events on it.

# EVENTS IN DOM

HTML DOM allows JavaScript to react to HTML events:

A JavaScript can be executed when an event occurs, like when a user clicks on an HTML element.

Examples of HTML events: on click

- When a user clicks the mouse
- When a web page has loaded
- When an image has been loaded
- When the mouse moves over an element
- When an input field is changed
- When an HTML form is submitted
- When a user strokes a key

```jsx
<h2 onclick="this.innerHTML='Ooops!'">Click on this text!</h2>
//display oops when clicked
<h1 onclick="changeText(this)">Click on this text!</h1>
<script>
function changeText(id) {
  id.innerHTML = "Ooops!";
}
</script>
//fuction used to call the html event
```

HTML events Attributes-

1,The onchange Event

The `onchange` event is often used in combination with validation of input fields.

```jsx
Enter your name: <input type="text" id="fname" onchange="upperCase()">

<script>
function upperCase() {
  const x = document.getElementById("fname");
  x.value = x.value.toUpperCase();
}
</script>
```

2,the onload Event

The onload and onunload events are triggered when the user enters or leaves the page.

```jsx
<script>
function checkCookies() {
  var text = "";
  if (navigator.cookieEnabled == true) {
    text = "Cookies are enabled.";
  } else {
    text = "Cookies are not enabled.";
  }
  document.getElementById("demo").innerHTML = text;
}
</script>
```

**Add an Event Handler to an Element:**

```jsx
<button id="myBtn">Try it</button>

<script>
document.getElementById("myBtn").addEventListener("click", function() {
  alert("Hello World!");
});
</script>
```

# session storage

allow to save key/value in we browser.

the session storage object stores data only for a session.

the data stored will be deleted when browser is closed.

methods and properties

sessionstorage.setitem(key,value)-store key/value pair

sessionstorage.getitem(key,value)-get the value by key

sessionstorage.removeitem(key,value)-remove key with it value

sessionstorage.clear()-delete

sessionstorage.key(index)-get the key on given postion

sessionstorage.length- the number of stored items

we use assassin story to when the user goes to browser the user data will be destroyed 

```jsx
sessionstorage.setItem('name','abebe')
//the inspect applicaton n key name value abebe
//after commenting and closing the web page and refresed/ reopend it
//the variable won't be accessable no more 
```

# local storage

a method of storing key/value pairs of information when browser even after refreshing and commenting the code the data still remain in application.

only store data as a string

```jsx
<script text="javascript">
let myobj = {
name:"dom",age:56
};
let myobj_serialized=JSON.stringfiy(myobj);
//we change it to string form because local storage only accept sting form
//output JSON way only stringify
localstorage.setItem("myobj",myobj_serialized);
console.log (localstorage);
//for javascript objectformat
let myobj_deserialized=JSON.parse(localstorage.getItem("myobj"));
console.log(myobj_deserialized);
</script>
```
