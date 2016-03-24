# Explore \coloredtext{LightGreen}{CSS} Properties
\label{cha:ch3}

In this chapter, we will inspect the CSS properties and how we can make good use of them, but we won't cover all of the CSS properties but to mention common ones.

## \coloredtext{LightGreen}{CSS} Colors
\label{sec:section3_1}

### Specifing Colors

First of all, let's inspect the CSS colors, there are three ways to specify the color :

- **Valid color names** EX. `red`, `Red` or `RED` (case are insensitive)
- **Hexadecimal Values** EX. `#ff0000` or `#FF0000` (case are insensitive)
- **RGB Values** EX. `rgb(255, 0, 0)`
- **RGBA Values** Ex. `rgba(255, 0, 0, 0.5)`

**Valid color names** is easy, which is the name of the color that can be recognized or supported by CSS.

**Hexadecimal values** are the form `#RRGGBB`, where `RR` stands for **red value**, `GG` stands for **green value** and `BB` stands for **blue value**. Each of them are all valued from `00` to `FF` (or `ff`, case are insensitive), for example, `#0000FF`(or `#0000ff`) stands for the blue color due to the `BB` portion has the highest value than the others. 

If you want to search for the color hexadecimal values or RGB values, you may reference this page : [Color HEX](http://www.color-hex.com) ([http://www.color-hex.com](http://www.color-hex.com))

**RGB values** which stands for `red`, `green` and `blue`, for instance, `rgb(0,255,0)` stands for `green` because the intensity of the green color has the highest value while the others have no intensity. The value of the intensity is between **0 ~ 255**.

**RGBA values** are the extension of the **RGB values** for one more parameter, which is called the **alpha channel** (so the **A** in **RGBA** stands for **alpha value**), checkout for section 3.1.2 .

There still have **HSL** and **HSLA** color specifier, but we think it is sufficient for you to specify the colors. (Wiki of HSL : [https://en.wikipedia.org/wiki/HSL_and_HSV](https://en.wikipedia.org/wiki/HSL_and_HSV))

### RGB & RGBA Values

![Color Wheels\label{captioned_image}](images/CH3/color_wheel.png)

- Image from [https://gastonsanchez.files.wordpress.com/2012/08/colorwheel.png](https://gastonsanchez.files.wordpress.com/2012/08/colorwheel.png)

We may want to discuss more about the RGB values, in the **Figure 3.1** this is the color wheel which specifies the RGB value cooresponding to the color it would look like.

![RGB Shades of Grey Values Sheet\label{captioned_image}](images/CH3/shades.gof.gif)

- Image from [http://www.dylanfisher.com/blog_images/hex_grayscale_001.gif](http://www.dylanfisher.com/blog_images/hex_grayscale_001.gif)

In **Figure 3.2**, it shows when the each of the RGB intensity are all equals, the larger of the intensity, the brighter the color you will get.

![RGBA in CSS3\label{captioned_image}](images/CH3/rgba.png)

- Image from [http://fellowtuts.com/wp-content/uploads/sites/3/2014/03/what-is-rgba-in-css.png](http://fellowtuts.com/wp-content/uploads/sites/3/2014/03/what-is-rgba-in-css.png)

**RGBA** values are new in **\coloredtext{LightGreen}{CSS3}**, it allows you specify the **alpha value**, which determines the opacity of your color values. The alpha value can be specified between **0 ~ 1**, the more closer to 1, the more the color be opaque.

### Using the "Opacity" \coloredtext{LightGreen}{CSS} Property

There's one more interesting thing, you can directly specify the opacity of the content, for example (Listing~\ref{code:css_opacity}), we specify the `opacity` values internally in order to see the difference between each image :

\begin{codelisting}
\codecaption{CSS inline styling example.}
\label{code:css_opacity}
```html
<!DOCTYPE html>
<html>
<head>
  <title>Example</title>
<style>
  img { 
    max-width: 15%; 
    background-color: #ffe4a3; 
    margin: 10px; 
  }
</style>
</head>
<body>
  <img src="http://www.nakulpathak.com/assets/projects/rails_api-
  a6bf58d9a9826f72fe05ad85079ee88111294b1c4061718ae06f0a7dbca39963.png" 
  alt="ruby-icon" style="opacity: 1">
  <img src="http://www.nakulpathak.com/assets/projects/rails_api-
  a6bf58d9a9826f72fe05ad85079ee88111294b1c4061718ae06f0a7dbca39963.png" 
  alt="ruby-icon" style="opacity: 0.8">
  <img src="http://www.nakulpathak.com/assets/projects/rails_api-
  a6bf58d9a9826f72fe05ad85079ee88111294b1c4061718ae06f0a7dbca39963.png" 
  alt="ruby-icon" style="opacity: 0.6">
  <img src="http://www.nakulpathak.com/assets/projects/rails_api-
  a6bf58d9a9826f72fe05ad85079ee88111294b1c4061718ae06f0a7dbca39963.png" 
  alt="ruby-icon" style="opacity: 0.4">
  <img src="http://www.nakulpathak.com/assets/projects/rails_api-
  a6bf58d9a9826f72fe05ad85079ee88111294b1c4061718ae06f0a7dbca39963.png" 
  alt="ruby-icon" style="opacity: 0.2">
</body>
</html> 
```
\end{codelisting}

![Result webpage\label{fig:captioned_image}](images/CH3/Capture3-1.png)

But for the reminder, the `opacity` property **changes the entire opacity of the content**, so the opacity not only affected on the `background-color` property but also the opacity of the `img` content as well.

## \coloredtext{LightGreen}{CSS} Backgrounds
\label{sec:section3_2}


## \coloredtext{LightGreen}{CSS} Box Model Properties
\label{sec:section3_3}

### \coloredtext{LightGreen}{CSS} Style Padding

### \coloredtext{LightGreen}{CSS} Style Margin

### \coloredtext{LightGreen}{CSS} Style Border

### \coloredtext{LightGreen}{CSS} Dimensional Properties


## \coloredtext{LightGreen}{CSS} Styling Each HTML Elements
\label{sec:section3_4}

### \coloredtext{LightGreen}{CSS} Style Fonts

### \coloredtext{LightGreen}{CSS} Style Text

### \coloredtext{LightGreen}{CSS} Style Links

### \coloredtext{LightGreen}{CSS} Style Images

### \coloredtext{LightGreen}{CSS} Style Lists

### \coloredtext{LightGreen}{CSS} Style Tables

## \coloredtext{LightGreen}{CSS} Layout
\label{sec:section3_5}

### \coloredtext{LightGreen}{CSS} Display

### \coloredtext{LightGreen}{CSS} Position

### \coloredtext{LightGreen}{CSS} Float and Clear

### \coloredtext{LightGreen}{CSS} Alignment





















