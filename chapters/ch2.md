# Webpage Stylist : \coloredtext{LightGreen}{CSS}
\label{cha:ch2}

Welcome to the second chapter of the book, in this chapter, you will learn the basics of **\coloredtext{LightGreen}{CSS}** (**Cascading Style Sheets**), from the concept of the box model, block or inline stylings and more. After completed this chapter, we should make good use of HTML and CSS to make some static webpage templates.

## Brief Introduction to \coloredtext{LightGreen}{CSS}
\label{sec:section2_1}

Cascading Style Sheets is a kind of **style sheet language** for describing the stylings of the HTML document. It can do many works such as separating contents of the page ,rendering specific layouts, changing the size, the font, the border...etc. CSS can improve the accessibility of the content, provide more flexibility and control in the specification of presentation characteristics, enable **multiple HTML pages to share formatting by specifying the relevant CSS in a separate .css file**, and **reduce complexity** and **repetition in the structural content**.

## \coloredtext{LightGreen}{CSS} Syntax Overview
\label{sec:section2_2}

So, lets start by inspecting the CSS syntax, there are "three" ways to add CSS stylings into an HTML document, **inline CSS**, **internal CSS** and **external CSS**.

### Inline \coloredtext{LightGreen}{CSS} Styling

Inline CSS styling is the most simple way to add the style, you just simply assign a `style` attribute in any element in the HTML document, such as (Listing~\ref{code:css_syntax_1}) :

\begin{codelisting}
\codecaption{CSS inline styling example.}
\label{code:css_syntax_1}
```html
<body>
  <h1> This is the header. </h1>
  <hr>
  <p style="color: blue;"> This is the paragraph, the paragraph is blue.</p>
</body>
```
\end{codelisting}

(Should display result image)

You can see that the value of the style attribute is :

```css
color: blue;
```

You can see that CSS syntax is easy, specify the **CSS property** (color) with its **value** (blue), and ends with a semi-colon, you have assigned the CSS property into the HTML element.

However, what if *you have many properties to add on a simgle HTML element*? Or what if *you have hundreds or thousands of same type of elements with same CSS property*, do you really think that you should add each tag with the property inlinely? Consider the next 
technique to add CSS with your HTML document.

### Internal \coloredtext{LightGreen}{CSS} Styling

Internal CSS styling means not to directly apply the CSS property to specific HTML tag, rather to use the `<style>` tag which contents need to *select* the HTML tag and apply the CSS property with it, consider the example below (Listing~\ref{code:css_syntax_2}) :

\begin{codelisting}
\codecaption{CSS internal styling example.}
\label{code:css_syntax_2}
```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
  <style>
    p { 
      color: blue; 
      background-color: yellow;
    }
    h1 {
      color: red;
    }
  </style>
</head>
<body>
  <h1>This is the header, the header is red.</h1>
  <hr>
  <p>This is the paragraph, the paragraph is blue with yellow background.</p>
</body>
</html>
```
\end{codelisting}

(Should display result image)

By inspecting one CSS code block :

```css
p {
  color: blue;
  background-color: yellow;
}
```

It provides more information about CSS, you can see that `p` is *selecting* the `<p>` element which should be add the CSS property listed below :

- `color: blue`
- `background-color: yellow`

They are nested by the **curly brackets**, and the part that selecting the elements is called **CSS selector**. So the basic syntax of CSS would be presented below :

```css
CSS selector {
  CSS property 1: value 1;
  CSS property 2: value 2;
  CSS property 3: value 3;
  ...
}
```

Well, its good that we can finally gather all CSS content into a single tag, but what if you have multiple pages adding the same CSS content, do you *think that it is a good way just copy and paste it into each HTML file*? Or thinking that why shouldn't we **separate** HTML and CSS into different file? Well, let's explore!

### External \coloredtext{LightGreen}{CSS} Styling

Now, to show you how separating the HTML and CSS works, lets just create an "example" folder with an "example.html" file in it, this is the content of the HTML file (Listing~\ref{code:css_syntax_3}) :

\begin{codelisting}
\codecaption{HTML file example.}
\label{code:css_syntax_3}
```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
</head>
<body>
  <h1>This is the header.</h1>
  <hr>
  <p>This is the paragraph.</p>
</body>
</html>
```
\end{codelisting}

(Should display result image)

And now, in the same directory, let's create another file called "example.css", please remember to add the ".css" prefix in order to specify that it is a kind of CSS file, now we can edit the file now (Listing~\ref{code:css_syntax_4}) :

\begin{codelisting}
\codecaption{External CSS file content.}
\label{code:css_syntax_4}
```css
p {
  color: blue;
  background-color: yellow;
}
h1 {
  color: red;
}
```
\end{codelisting}

But how should we *link* between the HTML and CSS file? We can use the `<link>` tag with the `rel` attribute with the value `stylesheet`, the `type` attribute with the value `text/css`, and finally, use the `href` to reference to your CSS file, in this case, we should append this line into the "example.html" :

```html
<link rel="stylesheet" type="text/css" href="example.css">
```

Notice that `<link>` tag is a kind of single tag and should be placed between the `<head>` tag in the HTML file (Listing~\ref{code:css_syntax_5}) :

\begin{codelisting}
\codecaption{Use <link> tag to include external CSS file.}
\label{code:css_syntax_5}
```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
  <link rel="stylesheet" type="text/css" href="example.css">
</head>
<body>
  <h1>This is the header.</h1>
  <hr>
  <p>This is the paragraph.</p>
</body>
</html>
```
\end{codelisting}

(Should display result image)

And now, you will have your style appended in the HTML file by including the CSS file.

### Cascading Precedence

However, here comes a question, what if we use all three techniques of CSS stylings, what is the order or the precedence of the CSS styles?

We can say that all the styles will **"cascade"** into a **"imaginary" style sheet** by the following rules, where the former one has the highest priority and the latter one has the lowest priority :

- Inline **\coloredtext{LightGreen}{CSS}** styling
- Internal **\coloredtext{LightGreen}{CSS}** styling
- External **\coloredtext{LightGreen}{CSS}** styling

So, assume that you specified the CSS property in the external file, such as :

```css
p {
  color: red;
}
h1 {
	color: blue;
}
```

You can override this rule by using the internal styling or inline styling :

```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
  <link rel="stylesheet" type="text/css" href="example.css">
  <!-- Overriding the CSS style property -->
  <style>
    p {
      color: blue; 
    }
  </style>
</head>
<body>
  <h1 style="color: red;">This is the header.</h1>
  <hr>
  <p>This is the paragraph.</p>
</body>
</html>
```

(Should display result image)

## Common Used \coloredtext{LightGreen}{CSS} Selectors
\label{sec:section2_3}

Now, we should dive deeply into the CSS selectors, it can help us to select or filter some HTML tags in order to apply styles on specific elements.

### Element Selector (Direct Selection)

We have just shown how to select element directly in the previous section, but for completeness, we will present the example again, these are the element selectors, each of them select all specific element. 

```css
/* Comments goes here in CSS */

p /* Select all <p> elements */ {
  color: blue; 
}
h1 /* Select all <h1> elements */ {
  color: red;
}
```

Notice that every CSS comments are nested by `/* */`. By apply the styling listed above in the HTML file (Listing~\ref{code:css_selector_1}), you should get :

\begin{codelisting}
\codecaption{.}
\label{code:css_selector_1}
```html
<body>
  <h1>This is the header.</h1>
  <hr>
  <p>This is the first paragraph.</p>
  <p>This is the second paragraph.</p>
  <p>This is the third paragraph.</p>
</body>
```
\end{codelisting}

(Should display result image)

You can also select multiple elements directly with the same style by separating the seletors by commas.

```css
h1, h3, h5 { color: red; }
```

Applying the CSS listed above with the HTML file (Listing~\ref{code:css_selector_2}), you should get:

\begin{codelisting}
\codecaption{Sample HTML file.}
\label{code:css_selector_2}
```html
<body>
  <h1>This is the "h1" header.</h1>
  <h2>This is the "h2" header.</h2>
  <h3>This is the "h3" header.</h3>
  <h4>This is the "h4" header.</h4>
  <h5>This is the "h5" header.</h5>
  <h6>This is the "h6" header.</h6>
</body>
```
\end{codelisting}

(Should display result image)

### ID Selectors

Usually, when talking about IDs, the property of the ID is the **uniqeness**, we can give the `id` attribute in any kind of HTML tags, such as (Listing~\ref{code:css_selector_3}) :

\begin{codelisting}
\codecaption{Appending ID example.}
\label{code:css_selector_3}
```html
<body>
  <p>This is the paragraph.</p>
  <p>This is the paragraph.</p>
  <p id="unique_paragraph">This is the paragraph with an id.</p>
  <p>This is the paragraph.</p>
</body>
```
\end{codelisting}

We can `select` the ID by using the **sharp sign (#)** followed by the ID name, the syntax to select the ID is :

```css
#ID_NAME { CSS content }
```

Let's append the CSS style (Listing~\ref{code:css_selector_4}), and it will become like this :

\begin{codelisting}
\codecaption{Styling with ID.}
\label{code:css_selector_4}
```css
p { color: red; }
#unique_paragraph { color: blue; }
```
\end{codelisting}

(Should display result image)

### Class Selectors

If you can assign styles in specific "ID", you can also assign `class` attribute to any tags, but the difference between `class` and `id` is that, `class` can assign to multitple HTML elements (not need to be of same type), `id` can only assign to one element.

So here we have a sample HTML file (Listing~\ref{code:css_selector_5}) :

\begin{codelisting}
\codecaption{Appending Class example.}
\label{code:css_selector_5}
```html
<body>
  <h1 class="example">Header</h1>
  <p>Paragraph 1</p>
  <p class="example">Paragraph 2</p>
  <p>Paragraph 3</p>
  <p class="example">Paragraph 4</p>
</body>
```
\end{codelisting}

To select all the tags with the same class name, just add a dot following the class name :

```css
.CLASS_NAME { CSS content }
```

Let's append the CSS style in Listing~\ref{code:css_selector_6}, and you will get :

\begin{codelisting}
\codecaption{Styling with Class.}
\label{code:css_selector_6}
```css
p { color: red; }
.example { color: blue; }
```
\end{codelisting}

(Should display result image)

How about we want all the `<p>` elements with class "example" and the `<h1>` element with the class "example" display different color? You can try this syntax to specify specific tags following with the class selector syntax :

```css
ELEMENT_NAME.CLASS_NAME { CSS content }
```

Let's append this CSS style in Listing~\ref{code:css_selector_7}

\begin{codelisting}
\codecaption{Styling with Class with different elements.}
\label{code:css_selector_7}
```css
p { color: red; }
p.example  { color: blue; }
h1.example { color: green; }
```
\end{codelisting}

(Should display result image)

### Sub-Element Selector

Sometimes we want to style specific element which is nested by another kind element, such as the example HTML file below (Listing~\ref{code:css_selector_8}) :

\begin{codelisting}
\codecaption{Styling with Class with different elements.}
\label{code:css_selector_8}
```html
<body>
  <h1>Several List :</h1>
  <ul id="list-1">
    <li>C</li>
    <li>C++</li>
    <li>C#</li>
  </ul>
  <ul id="list-2">
    <li>Ruby</li>
    <li>Rails</li>
  </ul>
</body>
```
\end{codelisting}

We want all the `<li>` elements that nested by the `<ul>` with different `id` styled with different color, the syntax of selecting the inner element or sub-element is :

```css
ELEMENT SUB-ELEMENT { CSS content }
```

So, in order to satisfy the condition that described above, we can append the CSS content below (Listing~\ref{code:css_selector_9}) :

\begin{codelisting}
\codecaption{Styling the sub-element with CSS example.}
\label{code:css_selector_9}
```css
#list-1 li { color: red; }
#list-2 li { color: green; }
```
\end{codelisting}

(Should display result image)

## \coloredtext{CornflowerBlue}{HTML} Block & Inline
\label{sec:section2_4}








































