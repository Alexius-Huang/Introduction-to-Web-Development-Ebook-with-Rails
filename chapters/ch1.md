# Webpage Constructor : \coloredtext{CornflowerBlue}{HTML}
\label{cha:ch1}

Hello readers, welcome to the world of \coloredtext{CornflowerBlue}{Web Development!} When talking about web development, everything will be started from learning **HTML** and **CSS** syntax, which we can create **static webpages**. After that, you can use **JavaScript** with its library **jQuery** to create **dynamic webpages**, such as the *dropdown menu*, the *animation* and more!

![HTML/CSS/JavaScript icons\label{fig:captioned_image}](images/CH1/front-end.png)

(Image by [http://davidmles.com/blog/frontend-technologies/](http://davidmles.com/blog/frontend-technologies/))

Overall, these (HTML, CSS and JavaScript) are all associated with **\coloredtext{CornflowerBlue}{front-end}**, which are the \coloredtext{CornflowerBlue}{visable contents when you browsing webpages}. Nevermind of all these lind of terms in case you didn't know, we will gradually dig into it and learn some useful techniques.

## Brief Introduction to \coloredtext{CornflowerBlue}{HTML}
\label{sec:section1_1}

**\coloredtext{CornflowerBlue}{HTML}**, which stands for [Hypertext Markup Language](https://en.wikipedia.org/wiki/HTML), is a standard markup language to create the structure of web pages or web applications along with CSS and JavaScript. HTML is not a kind of programming language, but *browsers* (such as Internet Explorer, Chrome, Firefox, Safari, Opera...) can read HTML files and **render** the visible contents on the webpages.

## \coloredtext{CornflowerBlue}{HTML} Syntax Overview
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

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-1.png)

Each line contains a pair or pairs of angle brackets, these are the basic **HTML tags** or **elements** of the HTML document. Notice that *most* of the HTML elements have starting tags and ending tags, and in order to specify the ending tag, you can see that it always contains a slash(/) sign, such as ```<html>``` and ```</html>```. (Not all of the HTML elements have both starting and ending tags.)

By inspecting each lines, the following are the explainations of Listing~\ref{code:html_structure} :

- ```<!DOCTYPE html>``` is a kind of **declaration tag**, this line specified that this is the HTML document.
- ```<html>``` element describe the content of the HTML document, it should be a pair in the document.
- ```<head>``` provides information of the document, such as the [*encode type*](http://www.w3schools.com/html/html_charset.asp) of the document, [*metadata*](https://en.wikipedia.org/wiki/Meta_element) or the included CSS/JS files, these details will appear as we process through the ebook.
- ```<body>``` is the main tag contains or nesting visible contents of the document.
- ```<h1>``` is **header** tag, defines the **header** of the content.
- ```<p>``` is **paragraph** tag, defines the **paragraph**.
- ```<!-- comments here -->``` is **comment** tag, the content in this tag would not affect the content of the webpage.

## Common Used \coloredtext{CornflowerBlue}{HTML} Tags
\label{sec:section1_3}

Knowing that HTML documents are composed by elements (or tags), we now introduce some useful tags you might use the most in the future :

### Headers

Headers are a sequence of tags from ```<h1>``` to ```<h6>```, the lower of the number, the larger of the size of the header text (Listing~\ref{code:html_headers}) :

\begin{codelisting}
\codecaption{Headers example.}
\label{code:html_headers}
```html
<h1>This is the first header.</h1>
<h2>This is the second header.</h2>
<h3>This is the third header.</h3>
<h4>This is the fourth header.</h4>
<h5>This is the fifth header.</h5>
<h6>This is the sixth header.</h6>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-2.png)

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

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-3.png)


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

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-4.png)

### Add Images

HTML images are also simple to add, by using the ```<img>``` tag with the ```src``` and ```alt``` attribute. The attribute ```src``` stands for the word **source**, which means the source of the image file. The other attribute ```alt``` stands for the word **alternative**, which means when the browser somehow cannot find the source of the image (or maybe the image is missing in any reason), the image would display the content in the ```alt``` attribute. 

The syntax will be represented as :

```html
<img src="Image source" alt="Alternative content when the image unable to load."/>
```

(Notice that ```<img>``` tag appears not as a pair of tags, it should contain the slash sign followed by the right angle brackets!)

So what is the source of the image, one way is just specifiy its URL, for instance, to add the logo of the [Ruby Language](https://www.ruby-lang.org/en/), you can specify the URL of the logo and add short content of the icon in the ```alt``` attribute (Listing~\ref{code:html_image_1}) :

\begin{codelisting}
\codecaption{Example add image by specifying its URL.}
\label{code:html_image_1}
```html
<body>
  <img src="http://engineering.yp.com/img/ruby-logo.png" alt="The ruby logo">
</body>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-5.png)

(You may want to know how to resize images, this will be introduced in the next chapter.)

There is another way to add images, assume here is the folder where the "example.html" file and the image file "ruby-logo.png", they are stored (as in **should add figure**) , when the browser didn't expected to find image through the URL, it should find the image in the folder or the directory where the image was stored. In this example, the "example.html" should import the image as in Listing~\ref{code:html_image_2} :

![Example directory\label{fig:captioned_image}](images/CH1/ExampleDirectory.png)

\begin{codelisting}
\codecaption{Example add image by specifying its URL.}
\label{code:html_image_2}
```html
<body>
  <img src="./Images/ruby-logo.png" alt="The ruby icon">
</body>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-6.png)

Notice that the source follows the path from the current directory (a dot), to the "Images" folder, and to the image file.

### Paragraphs Format

Here are more specifics on ```<p>``` tag, you first need to realize that it is not sure whether how HTML will be displayed visually. In order to emphasize this point, try adding more whitespaces or new lines for example (Listing~\ref{code:html_paragraph_format_1}) :

\begin{codelisting}
\codecaption{Example for paragraph format.}
\label{code:html_paragraph_format_1}
```html
<h3>In Myself - Louisa May Alcott</h3>
<p>
  I do not ask for any crown
  But that which all may win;

  Nor try to conquer any world
  Except the one within.

  Be thou my guide until I find
  Led by a tender hand,

  The happy kingdom in myself
  And dare to take command.
</p>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-7.png)

It seems like the format didn't do us the favor, so, here we introduce another HTML element called **preformatted tag**, the ```<pre>``` tag. The text inside the ```<pre>``` element is displayed in a different font (Courier mostly), and it also preserves both spaces and line breaks (Listing~\ref{code:html_paragraph_format_2}) :

\begin{codelisting}
\codecaption{Example for paragraph format by using ```<pre>``` element.}
\label{code:html_paragraph_format_2}
```html
<h3>In Myself - Louisa May Alcott</h3>
<pre>
  I do not ask for any crown
  But that which all may win;

  Nor try to conquer any world
  Except the one within.

  Be thou my guide until I find
  Led by a tender hand,

  The happy kingdom in myself
  And dare to take command.
</pre>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-8.png)

Other paragraphs formatting such as the ```<br>``` tag means **line break**, for example (Listing~\ref{code:html_paragraph_format_3}) :

\begin{codelisting}
\codecaption{Line break tag example.}
\label{code:html_paragraph_format_3}
```html
<p>A paragraph with <br> a line break.</p>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-9.png)

The ```<hr>``` tag means **horizontal rule**, which defines a horizontal line, for example (Listing~\ref{code:html_paragraph_format_4}) :

\begin{codelisting}
\codecaption{Horizontal rule example.}
\label{code:html_paragraph_format_4}
```html
<h1>This is the header.</h1>
<hr>
<p>This is the paragraph.</p>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-10.png)

### Quotes

And now we are dealing **quotes**! First of all, to define short quotations, simply use the ```<q>``` tag as well, for example (Listing~\ref{code:html_quotes_1}) :

\begin{codelisting}
\codecaption{Short quotes example.}
\label{code:html_quotes_1}
```html
<p>
  Ruby is a language of careful balance. Its creator, Yukihiro “Matz” Matsumoto, 
  (paragraph ommitted), he has often said that he is <q>trying to make Ruby natural, 
  not simple,</q> in a way that mirrors life.
  <br>
  <small>Via <a href="https://www.ruby-lang.org/en/about/">Ruby Lang</a></small>
</p>

```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-11.png)

The quotes nested the sentence "trying to make Ruby natural, not simple". (And that is true!)

But how about long quotes? There HTML prepared another tag called ```<blockquote>```, usually by using this tag, the browser will indent the content inside the tag, for example (Listing~\ref{code:html_quotes_2}) :

\begin{codelisting}
\codecaption{Large quotes example.}
\label{code:html_quotes_2}
```html
<p>
  Ruby was conceived on February 24, 1993. In a 1999 post to the ruby-talk mailing 
  list, Ruby author Yukihiro Matsumoto describes some of his early ideas about the
  language:
  <blockquote>
    I was talking with my colleague about the possibility of an object-oriented
    scripting language. I knew Perl (Perl4, not Perl5), but I didn't like it really, 
    because it had the smell of a toy language (it still has). The object-oriented 
    language seemed very promising. I knew Python then. But I didn't like it, 
    because I didn't think it was a true object-oriented language — OO features 
    appeared to be add-on to the language. As a language maniac and OO fan for 
    15 years, I really wanted a genuine object-oriented, easy-to-use scripting 
    language. I looked for but couldn't find one. So I decided to make it.
  </blockquote>
  <br>
  <small>Via <a href="https://en.wikipedia.org/wiki/Ruby_(programming_language)">
  Ruby Wiki</a></small>
</p>

```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-12.png)


### Lists

There are two types of HTML lists, first is the unordered list, which use the tag ```<ul>``` to represent, each of the list item is nested by ```<li>```, for example (Listing~\ref{code:html_list_1}) :

\begin{codelisting}
\codecaption{Unordered list example.}
\label{code:html_list_1}
```html
<h2>Computer Languages :</h2>
<ul>
  <li>C++</li>
  <li>Java</li>
  <li>C#</li>
  <li>Python</li>
  <li>Ruby</li>
</ul>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-13.png)

Another type of list is the ordered list, which use the tag ```<ol>``` to represent, and each of the list item is also nested by ```<li>``` element, for example (Listing~\ref{code:html_quotes_2}) :

\begin{codelisting}
\codecaption{Large quotes example.}
\label{code:html_quotes_2}
```html
<h2>Steps to learn Web Development :</h2>
<ol>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
  <li>PHP, SQL/ Ruby on Rails/ other Web Framework</li>
</ol>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-14.png)


### Tables

Tables are also important format that describes the data or make the contents look well, every thing associated with the table should (obviously) nested by the ```<table>``` element. 

```html
<table>
  <!-- Table content goes here -->
</table>
```

By inspecting the structure of the table, table are the composed by table rows, which can be represented by the ```<tr>``` tag, lets say having three rows :

```html
<table>
  <tr> <!-- Row 1 --> </tr>
  <tr> <!-- Row 2 --> </tr>
  <tr> <!-- Row 3 --> </tr>
</table>
```

Now each table row can divided by several table data with the ```<th>``` or ```<td>``` element, ```<th>``` represents the table header whereas ```<td>``` represents the table data. Now we can construct a simple table, for instance (Listing~\ref{code:html_table_1}) :

\begin{codelisting}
\codecaption{HTML table example.}
\label{code:html_table_1}
```html
<table>
  <tr> <th>Name</th>  <th>Age</th> <th>Interest</th> </tr>
  <tr> <td>Max</td>   <td>20</td>  <td>Drawing</td>  </tr>
  <tr> <td>Allen</td> <td>18</td>  <td>Reading</td>  </tr>
</table>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-15.png)

Some table even have the main table caption on it, lets specify the caption of the table by using the element ```<caption>``` right after the first ```<table>``` element (Listing~\ref{code:html_table_2}) :

\begin{codelisting}
\codecaption{HTML table with a caption example.}
\label{code:html_table_2}
```html
<table>
  <caption>Info of the Students</caption>
  <tr> <th>Name</th>  <th>Age</th> <th>Interest</th> </tr>
  <tr> <td>Max</td>   <td>20</td>  <td>Drawing</td>  </tr>
  <tr> <td>Allen</td> <td>18</td>  <td>Reading</td>  </tr>
</table>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-16.png)

Sometime you can span more data cells into one row or one column, try spanning multiple rows in one column by using the ```rowspan``` attribute, for instance (Listing~\ref{code:html_table_3}) :

\begin{codelisting}
\codecaption{HTML table rowspan example.}
\label{code:html_table_3}
```html
<table>
  <tr> <th>Name</th>              <td>Max</td>                  </tr>
  <tr> <td rowspan="2">Email</td> <td>example@gmail.com</td>    </tr>
  <tr>                            <td>example@yahoo.com.tw</td> </tr>
</table>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-17.png)

Or, by using the ```colspan``` attrbuts to span multiple columns into one column (Listing~\ref{code:html_table_4}) :

\begin{codelisting}
\codecaption{HTML table colspan example.}
\label{code:html_table_4}
```html
<table>
  <tr> <th>Name</th> <th colspan="2">Email</th>                                </tr>
  <tr> <td>Max</td>  <td>example@gmail.com</td>  <td>example@yahoo.com.tw</td> </tr>
</table>
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH1/Capture1-18.png)

## Summery
\label{sec:section1_4}

Here is the list of the tags and elements we've walkthrough :

|**HTML Tag** | **Name** | **Description** |
| `<!DOCTYPE>` | Declaration tag | Declare the document type |
| `<html>` | HTML tag | Defines the HTML document |
| `<head>` | Head tag | Provides more information of the HTML document |
| `<body>` | Body tag | Provides visible webpage contents |
| `<h1>` ~ `<h6>` | Header tags | Defines the header of the document |
| `<!-- -->` | Comment tag | Explanation of the document |
| `<p>` | Paragraph tag | Describes the HTML paragraph |
| `<b>`| Bold tag | Display bolded text |
| `<strong>`| Strong tag | Display bolded text semantically **strong** |
| `<i>` | Italic tag | Display the italic text |
| `<em>` | Emphsizing tag| Display the italic text semantically *emphasized* |
| `<sub>` | Subscript tag | Display the subscripted text |
| `<sup>` | Superscript tag| Display the superscripted text |
| `<small>` | Small tag | Display relatively small text |
| `<mark>` | Mark tag | Display the marked text |
| `<del>` | Delete tag | Display the deleted text |
| `<ins>` | Insert tag | Display the inserted text |
| `<a>` | Anchor tag | Create an hyper referenced link |
| `<img>` | Image tag | Add images in the HTML document |
| `<pre>` | Preformatted tag | Display paragraphs which preserves both whitespaces and line breaks|
| `<br>` | Break tag | Defines new line in HTML document |
| `<hr>` | Horizontal rule tag | Defines an horizontal line which can separate contents in HTML document|
| `<q>` | Quote tag | Defines short quotation |
| `<blockquote>` | blockquote tag | Defines large quotation |
| `<ul>` | Unordered list tag | Defines an unordered list |
| `<ol>` | Ordered list tag | Defines an ordered list |
| `<li>` | List item tag | Defines a list item |
| `<table>` | Table tag | Specified the table content in HTML document |
| `<tr>` | Table row tag | Defines a row in the HTML table content |
| `<th>` | Table header tag | Defines a table header cell in the HTML table row content |
| `<td>` | Table data tag | Defines a table data cell in the HTML table row content |
| `<caption>` | Table caption tag | Defines the caption of the HTML table |

We covered most common used HTML elements in this book, however we havn't introduce some other important HTML tags or elements such as ```<div>``` or ```<form>``` tags, but nevermind, these will appear as we processs into the later chapters, all we recommend you to do is to familierize how to use the common HTML tags in order to prepare for Chapter~\ref{cha:ch3}.

And we also congratulate that you known the basic structure of the HTML elments and we are gonna proceed to learn how to style our HTML tags by using **\coloredtext{LightGreen}{CSS}**!

For more informations of the HTML elements, you can search the [W3School website](http://www.w3schools.com/html/default.asp) : http://www.w3schools.com/html/default.asp



































