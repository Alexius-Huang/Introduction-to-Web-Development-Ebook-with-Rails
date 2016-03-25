# Webpage Animator : \coloredtext{Orange}{JavaScript}
\label{cha:ch5}

We have already walkthrough \coloredtext{CornflowerBlue}{HTML} and \coloredtext{LightGreen}{CSS}, it's time to explore how to use \coloredtext{Orange}{JavaScript} to make dynamic webpages.

## Brief Introduction to \coloredtext{Orange}{JavaScript}
\label{sec:section5_1}

### Introduction

\coloredtext{Orange}{JavaScript} is a **high-level**, **object-oriented**, **dynamic**, **interpreted** programming language, it is one of the component, with HTML and CSS, as **World Wide Web** content production. 

Be aware that, despite its naming, **\coloredtext{Orange}{JavaScript}** has nothing related to **Java** programming language. Most of the time **\coloredtext{Orange}{JavaScript}** support front-end content (**client-side**), such as **p5.js**, **D3.js**, **React.js** and more! However, there appeared **server-side** implemented \coloredtext{Orange}{JavaScript} which is also well known as **Node.js**.

### Where to Put \coloredtext{Orange}{JavaScript}?

There are two main ways to put JavaScript code. The first way can be using the `<script>` tag which surrounds the JavaScript code. For example, try this (Listing~\ref{code:js_code_1}) :

\begin{codelisting}
\codecaption{Using `<script>` element.}
\label{code:js_code_1}
```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
</head>
<body>
  <p id="content">This is the paragraph.</p>
  <button onclick="say_hi()">Click me!</button>
  <!-- <script> Usually Placed inside the Bottom of the <body> -->
  <script>
    function say_hi(){
      document.getElementById("content").innerHTML = "Hello!";
    }
  </script>
</body>
</html>
```
\end{codelisting}

![Before clicking button\label{fig:captioned_image}](images/CH5/Capture5-1.png)
![After clicking button\label{fig:captioned_image}](images/CH5/Capture5-2.png)

We will talk about **JavaScript function** in later sections, but this example also show us that **JavaScript can manipulate DOM content**, which means it can modify the **document content**, DOM will be also presented in later sections.

Another way is alike "external CSS", we can create **.js** files in order to pack the JavaScript and then using the `<script>` element with the `src` attribute which specifies the JavaScript file. For example, in the directory we have two file, one is **example.html** and another is **example.js** file :

![Example folder\label{fig:captioned_image}](images/CH5/Capture5-3.png)

These are the codes stored in the HTML (Listing~\ref{code:html_sample}) and JS (Listing~\ref{code:js_sample}) file separately :

\begin{codelisting}
\codecaption{Sample HTML file.}
\label{code:html_sample}
```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
  <script src="example.js"></script>
</head>
<body>
  <p id="content">This is the paragraph.</p>
  <button onclick="change_content()">Click me!</button>
</body>
</html>
```
\end{codelisting}

\begin{codelisting}
\codecaption{Sample JS file.}
\label{code:js_sample}
```js
function change_content(){
  content = document.getElementById("content");
  content.innerHTML = "This paragraph is blue!";
  content.style.color = "blue";
}
```
\end{codelisting}

![Before clicking button\label{fig:captioned_image}](images/CH5/Capture5-4.png)
![After clicking button\label{fig:captioned_image}](images/CH5/Capture5-5.png)

## \coloredtext{Orange}{JavaScript} Data Types
\label{sec:section5_2}

To learn not only **\coloredtext{Orange}{JavaScript}** but also any programming languages, the recommended way is to clarify and figured out the **data types** of the programming language. 

### Strings

Everything start with **strings** seem to be easier, and also important how you manipulate the strings.

String data stored as a series of **characters** nested in *single quotes* or *double quotes*, both way are valid in JavaScript, for example, we define **variable** called `greeting` which stored the string value `"Hello! JavaScript!"` (Listing~\ref{code:js_string_1}) :

\begin{codelisting}
\codecaption{Define JavaScript String.}
\label{code:js_string_1}
```js
var greeting = "Hello! JavaScript!";
var greeting = 'Hello! JavaScript!';
```
\end{codelisting}

Here is another useful tool should be introduced, it is the **web browser console**, open an arbitrary page, for example, we open an empty HTML file, right click and select **Inspect Element** (or in Safari, use **command + shift + i**, in other browsers, use **F12**) :

![Browser\label{fig:captioned_image}](images/CH5/Capture5-9.png)

Then you will enter the page which is the developer tool for debugging, but this time we first enter the **console** part, we can run the JavaScript code interactively. We can try the example above :

![Browser\label{fig:captioned_image}](images/CH5/Capture5-10.png)

By the way, the **keyword** `var` in JavaScript **defines a variable**, variables can store any kind of data. The syntax of defining data is :

```js
// var variable_name = variable_value;
```

**Double slash** means **comments** in JavaScript, the browser will ignore the line with double slash. Another important thing is that **every JavaScript statements are ended with semicolon!** If you got some errors or something wrong with JavaScript, make sure to check each line of JavaScript whether thay are ended by semicolon.

You are also allowed to use quotes in JavaScript strings, as long as they don't match the surrounding quotes (Listing~\ref{code:js_string_2}) :

\begin{codelisting}
\codecaption{Define JavaScript String with quotes.}
\label{code:js_string_2}
```js
var greeting = "Say 'Hi!'";
var greeting = 'Say "Hi!"';
```
\end{codelisting}

Or, you can use slash sign to **escape** the character (Listing~\ref{code:js_string_3}) :

\begin{codelisting}
\codecaption{Escape character.}
\label{code:js_string_3}
```js
var js = "I am learning "JavaScript"!";        // Wrong
var js = "I am learning \"JavaScript\"!";      // Right
```
\end{codelisting}

So how do we print strings on the browser? Most of the time we can use the statement :

```js
// document.getElementById( Element ID ).innerHTML = string_value ;
```

which means it can put the string value in the specified ID of the HTML element in the document. Try this (Listing~\ref{code:js_string_4}) :

\begin{codelisting}
\codecaption{Print out JavaScript string.}
\label{code:js_string_4}
```html
<body>
  <p id="content"></p>
  <script>
    var greeting = "Hello! JavaScript!";
    document.getElementById("content").innerHTML = greeting;
  </script>
</body>
```
\end{codelisting}

![Result Page\label{fig:captioned_image}](images/CH5/Capture5-6.png)

Surprisingly, you can include the HTML elements into string value, and it will interpreted in the browser as the HTML elements, for instance (Listing~\ref{code:js_string_5}) :

\begin{codelisting}
\codecaption{Place HTML elements into JavaScript string.}
\label{code:js_string_5}
```html
<body>
   <p id="content"></p>
  <script>
    var greeting = "Hello! JavaScript!" + "<br>";
    var button = "<button onclick='change_content()'>Click me!</button>";
    var content = document.getElementById("content");
    
    content.innerHTML = greeting;
    
    function change_content(){
      content.innerHTML = "You clicked the button!";
      content.style.color = "red";
    }
  </script>
</body>
```
\end{codelisting}

![Before clicking button\label{fig:captioned_image}](images/CH5/Capture5-7.png)

![After clicking button\label{fig:captioned_image}](images/CH5/Capture5-8.png)

There are several important things in the example. First of all, by the `+` operator, you can combine strings. Secondly, we use :

```js
var content = document.getElementById("content");
```

which means we **store the HTML element** (which is specified by its ID) in the `content` variable, and it can help simplify the code, so we don't need to write :

```js
document.getElementById("content").innerHTML = greeting;

function change_content(){
  document.getElementById("content").innerHTML = "You clicked the button!";
  document.getElementById("content").style.color = "red";
}
```

which is too long and cumbersome. Lastly, the content does render the HTML code, and the `<button>` element specified the attribute called `onclick` which is a `JavaScript events`, it will be presented in later sections.

Lastly, most of the time you might want to get the length of the string, you can use the `length` method as well (Listing~\ref{code:js_string_6}) :

\begin{codelisting}
\codecaption{String length method.}
\label{code:js_string_6}
```js
var string = "Hello";
var length_of_string = string.length;  // 5
```
\end{codelisting}

### Numbers

Second type of the data is numbers, to define numbers, it is the same as we defined strings (Listing~\ref{code:js_number_1}) :

\begin{codelisting}
\codecaption{Define JavaScript number.}
\label{code:js_number_1}
```js
var number = 123;
var number = 123.00;
```
\end{codelisting}

JavaScript number can defined as decimals or without decimals just as the example above. 

You can also define the scientific numbers such as (Listing~\ref{code:js_number_2}) :

\begin{codelisting}
\codecaption{Define scientific JavaScript number.}
\label{code:js_number_2}
```js
var number = 123e5;  // number = 12,300,000.0
var number = 123e-5; // number = 0.00123
```
\end{codelisting}

But if you defined number in an invalid way, it would become `NaN` (Not a Number) (Listing~\ref{code:js_number_3}) :

\begin{codelisting}
\codecaption{Not a number type.}
\label{code:js_number_3}
```js
var number = 123 / "HELLO~~";  // number = NaN
var number = 123 / "123"; // number = NaN
```
\end{codelisting}

Using the `+` operator can result string concatenation (but depend on the sequence!) (Listing~\ref{code:js_number_4}) :

\begin{codelisting}
\codecaption{String concatenation result.}
\label{code:js_number_4}
```js
var will_result_to_string = "12" + 34 + "56" ; // "123456" => String
var will_result_to_string = 12 + 34 + "56"   ; // "4656" => String
```
\end{codelisting}

In the example above, the first line from left to right, first approach to string, so then the several of the data will automatically converted into strings and concatenate together. 

However, the second line of the first and second data are numbers, so they sum up first and then approaches the third data which the type is a string and then concatenate together.

### Booleans

Boolean values are easy to understand, it only have two kinds of states : `true` or `false`. By using the `Boolean()` function, you can inspect the state of the expressions or the value into boolean type data (or even you don't need to use the function), such as (Listing~\ref{code:js_boolean_1}) :

\begin{codelisting}
\codecaption{JavaScript Boolean.}
\label{code:js_boolean_1}
```js
Boolean(8 > 5); // true
8 > 5;          // true
```
\end{codelisting}

Anything with **real value** is `true` (Listing~\ref{code:js_boolean_2}) :

\begin{codelisting}
\codecaption{String concatenation result.}
\label{code:js_boolean_2}
```js
var w = "Hello!";
Boolean(w);  // true

var x = 2;
Boolean(x);  // true

var y = 123.456;
Boolean(y);  // true

var z = true;
Boolean(z);  // true

var zero = 0;
Boolean(zero); // true 
```
\end{codelisting}

Even when "0" value is `true` in JavaScript. However, the values listed below are `false` value in JavaScript boolean value (Listing~\ref{code:js_boolean_3}) :

\begin{codelisting}
\codecaption{String concatenation result.}
\label{code:js_boolean_3}
```js
var empty_string = "";
Boolean(empty_string);     // false

var minus_zero = -0 ;
Boolean(mimus_zero);       // false

var false_value = false;
Boolean(false_value);      // false

var undefined_value;
Boolean(undefined_value);  // false

var null_value = null;
Boolean(null_value);       // false

var nan_value = NaN;
Boolean(nan_value);        // false
```
\end{codelisting}

Notice that *negative zero* is `false`, `undefined` value which is the variable without assigning any kind of data is `false`. The most confusing problem is that, although `null` value represented `false`, but actually it is only "comparable" only to the `undefined` value so (Listing~\ref{code:js_boolean_4}) :

\begin{codelisting}
\codecaption{JavaScript Boolean.}
\label{code:js_boolean_4}
```js
null == true;      // false
null == false;     // false
// null isn't comparable to the Boolean values!!

null == undefined; // true
```
\end{codelisting}

Although it is weird, but for the new programmer, we don't need to stuck into this problem too deep, if you are curious on this, you might consult [Abstract Equality Comparison Algorithm](http://es5.github.io/#x11.9.3) as well. (Credited by the answer from [Stackoverflow](http://stackoverflow.com/questions/27632391/why-null-false-and-null-true-both-return-false?answertab=votes#tab-top))

### Arrays

**Arrays** is one of the useful data type which can store multiple values in a variable. Defining array is like defining strings, numbers or booleans (Listing~\ref{code:js_array_1}) :

\begin{codelisting}
\codecaption{Defining arrays.}
\label{code:js_array_1}
```js
var to_do_list = [ "Eat breakfast", "Do homework", "Programming JavaScript"];
```
\end{codelisting}

That's easy, and you can place multiple type of values (Listing~\ref{code:js_array_2}) :

\begin{codelisting}
\codecaption{Multiple data types in array.}
\label{code:js_array_2}
```js
var a = ["Hello", 123, true, undefined, null, 1 > 2 ];
// The last element in the defined array is `false`
```
\end{codelisting}

To call out the items in array, use the square brackets, and the index of the items are started by 0 (Listing~\ref{code:js_array_3}) :

\begin{codelisting}
\codecaption{Index of the array.}
\label{code:js_array_3}
```js
var to_do_list = [ "Eat breakfast", "Do homework", "Programming JavaScript"];

to_do_list[0]; // "Eat breakfast"
to_do_list[1]; // "Do homework"
to_do_list[2]; // "Programming JavaScript"
```
\end{codelisting}

You can modify the array item's content by directly assigning values (Listing~\ref{code:js_array_4}) :

\begin{codelisting}
\codecaption{Modify the items' content of the array.}
\label{code:js_array_4}
```js
var to_do_list = ["Eat breakfast", "Do homework", "Programming JavaScript"];

to_do_list[0] = "Eat lunch"; // "Eat breakfast"
to_do_list; // ["Eat lunch", "Do homework", "Programming JavaScript"]
```
\end{codelisting}

Similar to the strings, by using the `length` method in array, it can return the numbers of the items of the array (Listing~\ref{code:js_array_5}) :

\begin{codelisting}
\codecaption{Array `length` method.}
\label{code:js_array_5}
```js
var to_do_list = [ "Eat breakfast", "Do homework", "Programming JavaScript"];

to_do_list.length;  // 3
```
\end{codelisting}

You can add array items by using the `push()` method (Listing~\ref{code:js_array_6}) :

\begin{codelisting}
\codecaption{Array `push()` method.}
\label{code:js_array_6}
```js
var programming_lang = [];

programming_lang.push("C++");
// programming_lang[0] = "C++"
programming_lang.push("Python");
// programming_lang[1] = "Python"
programming_lang.push("JavaScript");
// programming_lang[2] = "JavaScript"

programming_lang;
// ["C++", "Python", "JavaScript"]
```
\end{codelisting} 

By the `pop()` method, you can call out and remove the last item of the array (Listing~\ref{code:js_array_7}) :

\begin{codelisting}
\codecaption{Array `pop()` method.}
\label{code:js_array_7}
```js
programming_lang;  // ["C++", "Python", "JavaScript"]

a = programming_lang.pop();  // "JavaScript"
programming_lang;        // ["C++". "Python"]

b = programming_lang.pop();  // "Python"
programming_lang;        // ["C++"]

c = programming_lang.pop();  // "C++"
programming_lang;        // []

a; // "JavaScript"
b; // "Python"
c; // "C++"
```
\end{codelisting} 

### Objects

Object is the most useful, important and the core data type of JavaScript, in this section we only introduce the basic concept of the objects and leave the rest of the details to Section~\ref{sec:section5_7}.

To define the object, it contains the **name : value** pair, here is the example (Listing~\ref{code:js_object_1}) :

\begin{codelisting}
\codecaption{Defining JavaScript Objects.}
\label{code:js_object_1}
```js
var person = {
  name:     "Maxwell",
  age:      20,
  interest: ["drawing", "programming", "watching movies"],
  live:     "Taipei, Taiwan"
}
```
\end{codelisting}

In the example above, we define an object as a variable named `person`, which contains several **properties**, such as `name`, `age`, `interest` and where he `live`. Object are defined with the curly brackets, each **name : value** pair are separated by a comma, so the syntax of defining object is easy :

```js
// var object_name = { name1: value1, name2: value2, name3: value3 ...}
```
From the example above, it tells us another important concept, you can use any kind of data type as a value of the properties just like we did in the arrays.

Lastly, in JavaScript, everything can be objects, and **array is also another kind of object** too! Well, you can think of the array using numbers as the index of the item, then the object use the **name** as the index of the item (Listing~\ref{code:js_object_2}) :

\begin{codelisting}
\codecaption{Access the object item.}
\label{code:js_object_2}
```js
var person = {
  name:     "Maxwell",
  age:      20,
  interest: ["drawing", "programming", "watching movies"],
  live:     "Taipei, Taiwan"
}

person["name"];     // "Maxwell"
person["age"];      // 20
person["interest"]; // ["drawing", "programming", "watching movies"]
person["live"];     // "Taipei, Taiwan"
```
\end{codelisting}

JavaScript object provides more confortable way to access the items, it is similar to calling the *methods* (Listing~\ref{code:js_object_3}) :

\begin{codelisting}
\codecaption{Access the object item by calling a method way.}
\label{code:js_object_3}
```js
var person = {
  name:     "Maxwell",
  age:      20,
  interest: ["drawing", "programming", "watching movies"],
  live:     "Taipei, Taiwan"
}

person.name;     // "Maxwell"
person.age;      // 20
person.interest; // "drawing", "programming", "watching movies"]
person.live;     // "Taipei, Taiwan"
```
\end{codelisting}

You can modify the object items by calling the item properties and assign new values, both ways are valid (Listing~\ref{code:js_object_4}) :

\begin{codelisting}
\codecaption{Access the object item.}
\label{code:js_object_4}
```js
var person = {
  name:     "Maxwell",
  age:      20,
  interest: ["drawing", "programming", "watching movies"],
  live:     "Taipei, Taiwan"
}

person["age"] = 18;
person.interest.push("listen rock music");
person;
// person = {
//   name:     "Maxwell",
//   age:      18,
//   interest: ["drawing", "programming", "watching movies", "listen rock music"],
//   live:     "Taipei, Taiwan"
// }
```
\end{codelisting}

More details of the JavaScript object will be presented in later sections.

## \coloredtext{Orange}{JavaScript} Operators
\label{sec:section5_3}

### Arithmetic Operators

### Assignment Operators

### Logical Operators

## \coloredtext{Orange}{JavaScript} Conditional Statements
\label{sec:section5_4}

### If...Else Statement

### Switch...Case Statement

## \coloredtext{Orange}{JavaScript} Looping Statement
\label{sec:section5_5}

### While Loop

### For Loop

### Break or Continue

## \coloredtext{Orange}{JavaScript} Functions
\label{sec:section5_6}

## \coloredtext{Orange}{JavaScript} Objects
\label{sec:section5_7}
