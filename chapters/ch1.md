# Brief Intro to \coloredtext{CornflowerBlue}{HTML} and \coloredtext{CornflowerBlue}{CSS}
\label{cha:ch1}

Hello readers, welcome to the world of \coloredtext{CornflowerBlue}{Web Development!} When talking about web development, everything will be started from learning **HTML** and **CSS** syntax, which we can create **static webpages**. After that, you can use **JavaScript** with its library **jQuery** to create **dynamic webpages**, such as the *dropdown menu*, the *animation* and more!

(should contain html css and js icons)

Overall, these (HTML, CSS and JavaScript) are all associated with **\coloredtext{CornflowerBlue}{front-end}**, which are the \coloredtext{CornflowerBlue}{visable contents when you browsing webpages}. Nevermind of all these lind of terms in case you didn't know, we will gradually dig into it and learn some useful techniques.

## Brief Introduction to \coloredtext{CornflowerBlue}{HTML}
\label{sec:section1_1}

**\coloredtext{CornflowerBlue}{HTML}**, which stands for [Hypertext Markup Language](https://en.wikipedia.org/wiki/HTML), is a standard markup language to create the structure of web pages or web applications along with CSS and JavaScript. HTML is not a kind of programming language, but *browsers* (such as Internet Explorer, Chrome, Firefox, Safari, Opera...) can read HTML files and **render** the visible contents on the webpages.

## HTML Syntax Overview
\label{sec:section1_2}

Well, let's just start viewing the fundamentals of HTML, here is the basic structure of which the document should look like (Listing~\ref{code:html_structure}) :

\begin{codelisting}
\codecaption{Basic structure of HTML document.}
\label{code:html_structure}
```html
<!DOCTYPE html>
<html>
  <head>
    <!-- The is the comment -->
    <title>This is the title.</title>
  </head>

  <body>
    <!-- Visible contents was nested by the <body> tag -->
    <h1>This is the header.</h1>
    <p>This is the paragraph.</p>
  </body>
</html>
```
\end{codelisting}

(should contain an result image)

Each line contains a pair or pairs of angle brackets, these are the basic **HTML tags** or **elements** of the HTML document. Notice that *most* of the HTML elements have starting tags and ending tags, and in order to specify the ending tag, you can see that it always contains a slash(/) sign, such as ```<html>``` and ```</html>```. (Not all of the HTML elements have both starting and ending tags.)

By inspecting each lines, the following are the explainations of Listing~\ref{code:html_structure} :

- ```<!DOCTYPE html>``` is a kind of **declaration tag**, this line specified that this is the HTML document.
- ```<html>``` element describe the content of the HTML document, it should be a pair in the document.
- ```<head>``` provides information of the document, such as the [*encode type*](http://www.w3schools.com/html/html_charset.asp) of the document, [*metadata*](https://en.wikipedia.org/wiki/Meta_element) or the included CSS/JS files, these details will appear as we process through the ebook.
- ```<body>``` is the main tag contains or nesting visible contents of the document.
- ```<h1>``` is **header** tag, defines the **header** of the content.
- ```<p>``` is **paragraph** tag, defines the **paragraph**.
- ```<!-- comments here -->``` is **comment** tag, the content in this tag would not affect the content of the webpage.

## Common Used HTML Tags
\label{sec:section1_3}

Knowing that HTML documents are composed by elements (or tags), we now introduce some useful tags you might use the most in the future :

### Formatting

- ```<b>``` and ```<strong>``` elements : Both of them defines **bold** text, but ```<strong>``` elements defines extra semantic "stronger" importance.


- ```<i>``` and ```<em>``` elements : Both of them defines *italic* text, but ```<em>``` elements defines extra semantic "emphasized" importance.

- ```<sub>``` and ```<sup>``` elements : ```<sub>``` tag defines a subscripted text where as ```<sup>``` tag defines superscripted text.

- ```<small>``` element : Namely, defines the small text relative to the normal sized text.

- ```<mark>``` element : ```<mark>``` tag defines the highlighted text by changing its background color of the text.

- ```<del>``` and ```<ins>``` elements : ```<del>``` tag defines *deleted* (removed) text, which with a line crossed directly to the text. ```<ins>``` tag defines *inserted* (added) text, which with a line appended below the text.

Example HTML document (Listing~\ref{code:html_formatting}) :

\begin{codelisting}
\codecaption{Example HTML formatting.}
\label{code:html_formatting}
```html
<body>
  <h1>Example</h1>
  
  <p>This is the <b>bolded text</b>.</p>
  <p>This is also <strong>bolded text</strong> but semantically "strong".</p>
  
  <p>This is the <i>italic text</i>.</p>
  <p>This is the <em>italic text</em> but semantically being "emphasized".</p>

  <p>This is the <sub>subscripted text</sub>.</p>
  <p>You can represent water in Chemistry as H<sub>2</sub>O.</p>

  <p>This is the <sup>superscripted text</sup>.</p>
  <p>You can represent tempearature as 25<sup>o</sup>C.</p>

  <p>The <small>text</small> looks smaller than the normal size.</p>

  <p>The <mark>text</mark> is being marked.</p>
  
  <p>The <del>text</del> is being cross out! (Deleted or removed.)</p>
  
  <p>The <ins>text</ins> has an underline. (Inserted or added.)</p>

</body>
```
\end{codelisting}

(should contain an result image)


### Create Links

HTML links are very easy to add, using the ```<a>``` tag (called **anchor** tag) and specified hyper references will create the link, the syntax is :

```html
<a href="The hyper reference goes here!"> Link Name </a>
```

You may noticed that inside the tag, there we specified the link reference by ```href```, this is called HTML **attribute**, which can provide more information on the HTML tags.

Create a link to the Ruby Softcover page will result as (Listing~\ref{code:html_link}) :

\begin{codelisting}
\codecaption{Example creating HTML link.}
\label{code:html_link}
```html
<body>
  <p>This is the link to <a href="https://www.softcover.io">Softcover</a> 
   index page.</p>
</body>
```
\end{codelisting}

(should contain an result image)

### Add Images

HTML images are also simple to add, by using the ```<img>``` tag with the ```src``` and ```alt``` attribute. The attribute ```src``` stands for the word **source**, which means the source of the image file. The other attribute ```alt``` stands for the word **alternative**, which means when the browser somehow cannot find the source of the image (or maybe the image is missing in any reason), the image would display the content in the ```alt``` attribute. 

The syntax will be represented as :

```html
<img src="Image source" alt="Alternative content when the image unable to load."/>
```

So what is the source of the image, one way is just specifiy its URL, for instance, to add the logo of the [Ruby Language](https://www.ruby-lang.org/en/), you can specify the URL of the logo and add short content of the icon in the ```alt``` attribute (Listing~\ref{code:html_image_1}) :

\begin{codelisting}
\codecaption{Example add image by specifying its URL.}
\label{code:html_image_1}
```html
<body>
  <img src="http://blogs.microsoft.co.il/blogs/shayf/WindowsLiveWriter/
  GettingStartedWithDynamicLanguages_B665/ruby_logo_2.png" alt="The ruby icon">
</body>
```
\end{codelisting}

(should contain an result image)

There is another way to add images, assume here is the folder where the "example.html" file and the image file "ruby_logo.png", they are stored (as in **should add figure**) , when the browser didn't expected to find image through the URL, it should find the image in the folder or the directory where the image was stored. In this example, the "example.html" should import the image as in Listing~\ref{code:html_image_2} :

(should contain the directory image)

\begin{codelisting}
\codecaption{Example add image by specifying its URL.}
\label{code:html_image_2}
```html
<body>
  <img src="/images/ruby_logo.png" alt="The ruby icon">
</body>
```
\end{codelisting}

(should contain an result image)

### Paragraphs and Quotes






































