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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-1.png)

You can see that the value of the style attribute is :

```css
color: blue;
```

CSS syntax is easy, specify the **CSS property** (color) with its **value** (blue), and ends with a semi-colon, you have assigned the CSS property into the HTML element.

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-2.png)

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

And now, in the same directory, let's create another file called "example.css", please remember to add the ".css" prefix in order to specify that it is a kind of CSS file. 

This should be the current state of your folder :

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-3.png)

Now we can edit the file now (Listing~\ref{code:css_syntax_4}) :

\begin{codelisting}
\codecaption{External CSS file content.}
\label{code:css_syntax_4}
```css
p {
  color: white;
  background-color: green;
}
h1 {
  color: blue;
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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-4.png)

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-5.png)

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-6.png)

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-7.png)

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-8.png)

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-9.png)

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-10.png)

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

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-11.png)

## \coloredtext{CornflowerBlue}{HTML} Block & Inline Elements
\label{sec:section2_4}

Now we learned how to use selectors to arrange the styles where the element we wanted to apply to, but that isn't enough, because, sometimes we want "a group" of element, or "a
piece of element" to apply CSS, but first, we will introduce the display type of the HTML element.

### Block Level Elements

The **block level** elements started on a new line and stretches up the full width of the page as far as possible. Common block level element are the `<p>` and `<h1>` ~ `<h6>` header tags, to verify its display property, we use the border to see how the block element displayed (Listing~\ref{code:html_display_1}) :

\begin{codelisting}
\codecaption{Display type of the block element.}
\label{code:html_display_1}
```html
<body>
  <h1>This is the header</h1>
  <hr>
  <p>This is the paragraph</p>
</body>
```
\end{codelisting}

```css
h1, p { border: 2px solid green; }
```

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-12.png)

(We will learn more details about border after several sections.) You can clearly see that the block element takes as full width of the page.

### Inline Level Elements

The **inline level** element doesn't started on a new line, however it only take up the width of the content. Common inline level element are the `<a>` or `<img>` tags, to verify its display property, we added the border to see how the inline element displayed (Listing~\ref{code:html_display_2}) :

\begin{codelisting}
\codecaption{Display type of the block element.}
\label{code:html_display_2}
```html
<body>
  <h1>This is the header</h1>
  <hr>
  <p>This is the paragraph with a <a href="#">Link</a> .</p>
</body>
```
\end{codelisting}

```css
a { border: 2px solid green; }
```

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-13.png)

You can see that the `<a>` element didn't start with a new line and the border only group the content of the `<a>` element.

### The `<div>` & The `<span>` Element

The `<div>` and the `<span>` elements are very useful tags to arrange your HTML content, but two of them behave differently. `<div>` tag is a kind of **block level** element while `<span>` tag is a kind of **inline level** element.

The `<div>` element often used as a **container** for other HTML elements, it is common to append the `class` or `id` attribute in order to style blocks of content. For example (Listing~\ref{code:html_display_3}) :

\begin{codelisting}
\codecaption{Display type of the block element.}
\label{code:html_display_3}
```html
<body>
  <div id="taiwan"> <!-- This is the container with ID named 'taiwan' -->
    <h3>Taiwan</h3>
    <p>
      Taiwan, officially the Republic of China, is a sovereign state in East Asia. 
      The Republic of China, originally based in mainland China, has since 1945 
      governed the island of Taiwan, which constitutes more than 99% of its 
      territory, as well as Penghu, Kinmen, Matsu, and other minor islands,
      following its loss of the mainland China territory in 1949 in the Chinese 
      Civil War. This remaining area is also constitutionally called the "Free 
      area of the Republic of China" which is not ruled by the Communist Party 
      of China in Beijing.
    </p>
  </div>
</body>
```
\end{codelisting}

```css
#taiwan {
  background-color: #259359;
  padding: 10px;
  border-radius: 5px;
}
#taiwan h3, #taiwan p { color: white; }
#taiwan h3 { font-family: "Times New Roman"; }
#taiwan p { font-family: helvetica; }
```

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-14.png)

Sometimes we want some specific content inside an element display different style, then we can make use of the `<span>` tag, this time we change color of some text in the paragraph showed in the previous example, using the `<span>` tag with the same class (Listing~\ref{code:html_display_4}) :

\begin{codelisting}
\codecaption{Display type of the block element.}
\label{code:html_display_4}
```html
<body>
  <div id="taiwan"> <!-- This is the container with ID named 'taiwan' -->
    <h3>Taiwan</h3>
    <p>
      <span class="yellow">Taiwan</span>, officially the Republic of China, is a 
      <span class="yellow">sovereign state in East Asia</span>. The Republic of 
      China, originally based in mainland China, has since 1945 governed the island 
      of Taiwan, which constitutes more than 99% of its territory, as well as 
      Penghu, Kinmen, Matsu, and other minor islands, following its loss of the 
      mainland China territory in 1949 in the Chinese Civil War. This remaining area 
      is also constitutionally called the <span class="yellow">"Free area of the 
      Republic of China"</span> which is not ruled by the Communist Party of China 
      in Beijing.
    </p>
  </div>
</body>
```
\end{codelisting}

```css
#taiwan {
  background-color: #259359;
  padding: 10px;
  border-radius: 5px;
}
#taiwan h3, #taiwan p { color: white; }
#taiwan h3 { font-family: "Times New Roman"; }
#taiwan p { font-family: helvetica; }
span.yellow { color: yellow; }
```

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-15.png)

Now, we have shown you from selecting the element to grouping the element to style, we are nearly approaching to introduce the styling properties you can apply. However, there is one more concept to prepare and you can finally make good use of these knowledges.

## \coloredtext{LightGreen}{CSS} Box Model
\label{sec:section2_5}

### What is the \coloredtext{LightGreen}{CSS} Box Model

This section will help you build the basic concept about the fundamentals of design and layout, **all the HTML elements can be viewed as boxes**, each of them consists from inner to outer, **content**, **padding**, **border** and **margin**.

![CSS Box Model.\label{figure:captioned_image}](https://daks2k3a4ib2z.cloudfront.net/55fba7ade2ae0be15df2b309/56c13fd6bf6d3281049d04ae_box-model.gif)

**Content** is the visible part which contains text or images, and the other visible part is the **border**, which **surrounds the content and the padding**. (Of course you can also set the border property to be transparent)

**Padding** the the transparent part that **clears the area between the border and the content**. **Margin** is also the transparent part but **clears the area between the HTML elements**.

### Layout Process Example

Let's view the example below, suppose we want to style the HTML document below (Listing~\ref{code:html_box_model_1}) :

\begin{codelisting}
\codecaption{Example HTML File.}
\label{code:html_box_model_1}
```html
<!DOCTYPE html>
<html>
<head>
  <title>Ruby Lang Layout Example</title>
</head>
<body>
  <h1>Ruby Lang</h1>
  <img src="https://elixirgraphics.com/previews/Ruby/rw_common/images/ruby_logo_3a
  .png" alt="ruby-logo">
  <p>Ruby is a dynamic, reflective, object-oriented, general-purpose programming
  language. It was designed and developed in the mid-1990s by Yukihiro "Matz" 
  Matsumoto in Japan.</p>
  <a href="https://www.ruby-lang.org/en/">Official Website!</a>
  <a href="http://tryruby.org/levels/1/challenges/0">Try Ruby!</a>
  <a href="https://rubymonk.com">Ruby Monk!</a>
</body>
</html> 
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-16.png)

We will make use of the knowledge we learned from Section~\ref{sec:section2_2}, Section~\ref{sec:section2_3} and Section~\ref{sec:section2_4}. First of all, let's add some `<div>` or `<span>` tags in order to separate the content and then we can apply styles differently. (Listing~\ref{code:html_box_model_2})

\begin{codelisting}
\codecaption{Separate contents by `<div>` or `<span>` element.}
\label{code:html_box_model_2}
```html
<body>
  <div class="container">
    <div id="ruby-lang-paragraph">
      <h1>Ruby Lang</h1>
      <img src="https://elixirgraphics.com/previews/Ruby/rw_common/images/ruby_logo
      _3a.png" alt="ruby-logo">
      <p><span class="highlight">Ruby</span> is a <span class="highlight">dynamic,
      reflective, object-oriented, general-purpose programming language</span>. It 
      was designed and developed in the mid-1990s by <span class="highlight">
      Yukihiro "Matz" Matsumoto</span> in Japan.</p>
    </div>
    <div id="links">
      <a href="https://www.ruby-lang.org/en/">Official Website!</a>
      <a href="http://tryruby.org/levels/1/challenges/0">Try Ruby!</a>
      <a href="https://rubymonk.com">Ruby Monk!</a>
    </div>
  </div>
</body>
```
\end{codelisting}

And now we can append CSS on the page! Start with the whole "container" part (You will learn the CSS properties in the next chapter) (Listing~\ref{code:html_box_model_3}) :

\begin{codelisting}
\codecaption{Style the container class.}
\label{code:html_box_model_3}
```css
div.container { 
  background-color: #f0ccde; 
  border: 10px groove #f7e5ee;
}
```
\end{codelisting}

It should look like this :

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-17.png)

You can see that the background is styled with the pink color, and the border is surrounding the content, but it seems that the content sticks the border, we should *clear the space between the content and the border*, that's how **padding** serve our needs!

Add the CSS padding property (Listing~\ref{code:html_box_model_3}) :

\begin{codelisting}
\codecaption{Use the padding property in the cotainer class.}
\label{code:html_box_model_3}
```css
div.container { 
  background-color: #f0ccde; 
  border: 10px groove #f7e5ee;
  padding: 15px;
}
```
\end{codelisting}

The layout of the container looks good :

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-18.png)

Now we start to style the inner part, start with the `<div>` part with and `id` attribute named `ruby-lang-paragraph` (Listing~\ref{code:html_box_model_4}) :

\begin{codelisting}
\codecaption{Add more CSS properties in the "ruby-lang-paragraph" id part.}
\label{code:html_box_model_4}
```css
#ruby-lang-paragraph {
  font-family: "Comic Sans MS", cursive, sans-serif;
  color: #a50052;
}
#ruby-lang-paragraph h1 { text-align: center; }
#ruby-lang-paragraph img { display: block; margin: 0 auto; }
span.highlight { color: #8b80b2; }
```
\end{codelisting}

Well, I like the pink theme :

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-19.png)

Finally, let us style the link part (Listing~\ref{code:html_box_model_5}) :

\begin{codelisting}
\codecaption{Add more CSS properties in the "links" id part.}
\label{code:html_box_model_5}
```css
#links a {
  font-family: Helvetica;
  background-color: #b8005c;
  color: white;
  text-decoration: none;
  border: 2px solid #f7e5ee;
  padding: 5px;
  border-radius: 3px;
}
#links a:hover {
  background-color: white;
  color: #b8005c;
}
```
\end{codelisting}

This is how it will display, try **hover** the link and it will change into another style (Just like in the style in the middle button. The special selector `a:hover` uses `CSS pseudo class`,which we will introduce briefly in the next chapter.):

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-20.png)

But the links, however, seems stick too close, so we might think that we need to **clear a space between the links (or the `<a>` elements)**, then recall that the margin from CSS box model can clear the area between elements, let's add this property (Listing~\ref{code:html_box_model_6}) :

\begin{codelisting}
\codecaption{Add more CSS properties in the "links" id part.}
\label{code:html_box_model_6}
```css
#links a {
  font-family: Helvetica;
  background-color: #b8005c;
  color: white;
  text-decoration: none;
  border: 2px solid #f7e5ee;
  padding: 5px;
  border-radius: 3px;

  margin: 5px;
}
#links a:hover {
  background-color: white;
  color: #b8005c;
}
```
\end{codelisting}

Then the buttons are separated in moderate width :

![Result webpage\label{fig:captioned_image}](images/CH2/Capture2-21.png)

This is how the web page styled with CSS, maybe there are so many CSS properties you havn't known yet, but we will walkthrough them in the next chapter!

## Summery
\label{sec:section2_6}

In this chapter we talked about the fundamental structure of CSS and the basic syntax of CSS (Section~\ref{sec:section2_2}), we also shown that there are three ways to add CSS into HTML documents :

- **Inline CSS**
- **Internal CSS**
- **External CSS**

with the former one (inline CSS) has the highest priority and the latter one has the lowest priority (external CSS). We also discussed the benefit of using different type of importing CSS into the HTML documents.

CSS syntax contains **CSS selectors** (Section~\ref{sec:section2_3}) which can select the elements to apply the styles, and the **CSS properties** with **CSS values** to provide the imformation to describe the layout type of the HTML elements.

Moreover, we introduced the **display type of the HTML elements** (Section~\ref{sec:section2_4}) that can catagorized into the **block level** or the **inline level** element. By making good use of the `<div>` and the `<span>` elements, you are able to arrange the content and the style more easily and logically.

Last but not least, we introduced the most important topic in Section~\ref{sec:section2_5}, which is the **CSS box model**, it can help you arrange and layout the content more readable and clear. And we also demonstrate the CSS layout process in the same section, in order to let you know how **box model** works on styling webpages.

In the next chapter, you are going to use the knowledge of the CSS basics to learn the CSS properties, the next chapter is going to be fun that we will discover more on different types of styling with CSS!
