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
var greeting = "Hello! JavaScript!";
```
\end{codelisting}

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

### Arrays

### Objects

## \coloredtext{Orange}{JavaScript} Variables
\label{sec:section5_3}

## \coloredtext{Orange}{JavaScript} Operators
\label{sec:section5_4}

### Arithmetic Operators

### Assignment Operators

### Logical Operators

## \coloredtext{Orange}{JavaScript} Conditional Statements
\label{sec:section5_5}

### If...Else Statement

### Switch...Case Statement

## \coloredtext{Orange}{JavaScript} Looping Statement
\label{sec:section5_6}

### While Loop

### For Loop

### Break or Continue

## \coloredtext{Orange}{JavaScript} Functions
\label{sec:section5_7}

## \coloredtext{Orange}{JavaScript} Objects
\label{sec:section5_7}
