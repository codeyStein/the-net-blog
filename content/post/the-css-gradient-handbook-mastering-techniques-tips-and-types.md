+++
title = "The CSS Gradient Handbook: Mastering Techniques, Tips, and Types"
description = "CSS gradients, a topic which doesn't seem of much importance at once. There is so much you can do with gradients in CSS I am honestly blown away. Before writing this article the only thing I knew was how to create basic two-colored gradients, (I sometimes forgot how to do that too), but now I realize how much more CSS gradients have to offer!"
date = 2023-09-11T03:00:41-06:00
tags = ['css', 'design']
draft = false
+++

![The CSS Handbook: Mastering Techniques, Tips, and Typesl](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/q64x492dwo8v5hmf7fc6.png)
CSS gradients, a topic which doesn't seem of much importance at once. There is *so much* you can do with gradients in CSS I am honestly blown away. Before writing this article the only thing I knew was how to create basic two-colored gradients, (I sometimes forgot how to do that too), but now I realize how much more CSS gradients have to offer!<!--more-->

## Table Of Contents
- [What Are CSS Gradients And How Do They Work?](#what-are-css-gradients-and-how-do-they-work)
- [Working with Linear Gradients](#working-with-linear-gradients)
  - [Changing Gradient Directions](#changing-gradient-directions)
  - [Using Angles](#using-angles)
- [Creating Gradients with Multiple Colors](#creating-gradients-with-multiple-colors)
- [Using Radial Gradients](#using-radial-gradients)
  - [Positioning The Center of a Gradient](#positioning-the-center-of-a-gradient)
  - [Radial Gradient Shape](#radial-gradient-shape)
  - [Sizing Radial Gradients](#sizing-radial-gradients)
- [Working with Conic Gradients](#working-with-conic-gradients)
  - [Positioning The Center of a Conic Gradient](#positioning-the-center-of-a-conic-gradient)
  - [Using Angles](#using-angles)
- [Creating Repeating Gradients](#creating-repeating-gradients)
  - [Repeating Linear Gradients](#repeating-linear-gradients)
  - [Repeating Radial Gradients](#repeating-radial-gradients)
  - [Repeating Conic Gradients](#repeating-conic-gradients)
- [Advanced Techniques](#advanced-techniques)
  - [Specifying Color Positions](#specifying-color-positions)
  - [Create Harsh Lines](#create-harsh-lines)
  - [Create Gradient Hints](#create-gradient-hints)
  - [Create Stacked Gradients](#create-stacked-gradients)
  - [Opacity and Overlays](#opacity-and-overlays)
- [Online Resources](#online-resources)
- [Final Thoughts](#final-thoughts)

# Gradient Magic: Elevate Your Web Design With CSS Gradients

## What Are CSS Gradients And How Do They Work?
You can set boring solid colors in CSS pretty easily, it's one of the first things we learn when learning CSS, however, you can also create smooth color gradients with CSS. Before writing this article, I honestly had no idea that you could do so much with gradients, I only knew how to make two-colored gradients; turns out, that gradients can do a lot more than that.

![The Mo' You Know Gif](https://media.giphy.com/media/d2YVk2ZRuQuqvVlu/giphy.gif)

Colors gradients in CSS are defined with the CSS `image` data type, meaning they can be used anywhere you can use the image data type. They are made by smoothly transitioning between two or [multiple colors](#creating-gradients-with-multiple-colors). There are three main types of gradients:
* [Linear Gradients](#working-with-linear-gradients) (goes directions: up, down, left, right, and diagonally),
* [Radial Gradients](#using-radial-gradients) (defined by their center point, then expands from that point),
* [Conic Gradients](#working-with-conic-gradients) (rotated around a center point)

However, you can also make some pretty cool patterns by [repeating gradients](#creating-repeating-gradients) using the functions: [`reapting-linear-gradient()`](#creating-repeating-gradients), [`reapting-radial-gradient()`](#repeating-radial-gradients), and [`reapting-conical-gradient()`](#repeating-conic-gradients) respectfully.

Basic syntax example:
```css
<gradient-type>-gradient(direction, color1, color2, color3, ...);
```

CSS gradients are rendered by the browser, meaning that they can be resized without any noticeable delay loss of quality, unlike traditional raster images.
## Working with Linear Gradients
Let's start with the basics, then work our way up. Linear gradients, you've probably used them. They create progress in a straight line. You need at least two colors to define a linear gradient, which will be shown in a top-down direction if no direction or angle is specified. 

Linear gradient syntax:
```CSS
linear-gradient(<direction-angle>, first-color, ..., last-color)
```

Here's a basic example:
```CSS
  .gradient {
		background-color: purple; // For browsers that do not support gradients, which shouldn't be a problem, will be treated as a fallback
		
	  background-image: linear-gradient(red, blue); // Will be shown if browser does support
  }
	```


![Basic linear gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o8zxulu6xikfuy22ui3c.png)

### Changing Gradient Directions
 By default, gradients progress from top to bottom, you can change this by writing the desired direction before specifying your colors, like this:
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: linear-gradient(to right, red, blue);
  }
``` 

![Linear gradient example using directions](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ovew2bzv6ctw6o8j0qzv.png)

Easy enough, right?
Here are some other direction options for linear gradients:
* (default) `to bottom` - sets the direction of colors to be north to south.
* `to top` - sets the direction of colors to be north to south.
* `to right` - sets the direction of colors to be west to east.
* `to left` - sets the direction of colors to be east to west.

You can also define diagonal angles using directions:
* `to bottom right` - sets the direction of colors to be northwest to southeast.
* `to bottom left` - sets the direction of colors to be northeast to south-est.
* `to top right` - sets the direction of colors to be southeast to northwest.
* `to top left` - sets the direction of colors to be southwest to south-east.

Simple example using to bottom right:

```CSS
  .gradient {
		background-color: purple;
		
	  background-image: linear-gradient(to bottom right, red, blue);
  }
  ```


![diagonal linear gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/gfp9s09kz6cie5p3w5ll.png)

### Using Angles
Accustomed to over-engineering things like the typical programmer? (JK, you can also use angles to achieve more specific angles) Don't worry, you can also use angles to define directions, like this:
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: linear-gradient(110deg, red, blue);
  }
  ```

![Linear gradient using angles example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/le258rpgbwy0y459hrrl.png)

Angles can be confusing. Here's a quick but very useful to use when working with angles, thanks [mdn web docks!](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images/Using_CSS_gradients#using_linear_gradients)

![](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_images/Using_CSS_gradients/linear_red_angles.png)
## Creating Gradients with Multiple Colors
You can also create gradients with multiple color stops too, you don't have to limit yourself to only two. You can [specify where you want your color stops to be](#specifying-color-positions), however, by default, they will be spaced evenly. 

Here's an example of a rainbow (7 colors) gradient with no direction or angle specified (top-down):
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: linear-gradient(red,orange,yellow,green,cyan,blue,violet);

  }
```

![rainbow top down gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/795voinnx3mbzqco3nrv.png)

However, you can also use directions:
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: linear-gradient(to right, red,orange,yellow,green,cyan,blue,violet);

  }
```

![rainbow to right gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9i7yphiwmiud0yxvqolp.png)

Or angles:
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: linear-gradient(70deg, red,orange,yellow,green,cyan,blue,violet);

  }
```

![Rainbow gradient example using angles](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tp5c0zpmrq0gew9494lu.png)

## Using Radial Gradients
Radial gradients are similar to linear gradients except, unlike linear gradients, they don't progress in a straight line but instead are defined by their center point and then expand from that point.

Radial gradient syntax:
```CSS
radial-gradient(<shape size> at <position>, color1, color2, color3, ...);
```

Like linear gradients, to create a simple radial gradient, you only need two colors. By default, the colors will be evenly distributed, and the shape will match the aspect ratio of its container, by default elliptical.

A simple radial gradient can be defined like this:
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: radial-gradient(red, blue);
  }
```
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/2dwtpcvmjo9n2pu5mni0.png)
### Positioning The Center of a Gradient
Radial gradients are defined by their center, however, you can also specify the center of the gradient using keywords (similar to how we position linear-gradients), percentages, or absolute values.

```CSS
  .gradient {
		background-color: purple;
		
	  background: radial-gradient(at 0% 45%, red, blue);
  }
```
![Positioning center of radial gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5elpecmwmx071p6i585p.png)

### Radial Gradient Shape
Radial gradients can have the shape of either a circle or ellipse; ellipse being the default value.

Here's an example of a circle radial gradient
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: radial-gradient(circle, red, blue);
  }

```
![circle radial gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/shuvu6rxr5i66wppx8ig.png)
### Sizing Radial Gradients
You can also specify the size of radial gradients, kind of like how you would specify the position of a linear-gradient.

There are 4 total keywords you could use to specify the size of a gradient:
* (default) `farthest-corner`
* `closest-corner`,
* `closest-side`,
* `farthest-side`

#### farthest-corner (default) example:
Makes the gradient reach the farthest corner of its container. This means it will extend from the center to the point where it is farthest from the center.
```CSS
  .gradient {
		background-color: purple;
		
  background-image: radial-gradient(
    ellipse farthest-corner at 90% 90%,
    red,
    yellow 10%,
    blue 50%,
    green
  );
}
```
![farthest-corner example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/78c84ax7dfidyhbkam6w.png)

#### farthest-side example
Makes the gradient reach the farthest side of its container. Meaning that it will extend from the center to the point where it's at the farthest point of the center, reaching the edge of its container.

I found this one a little confusing at first, as well as the difference between `farthest-corner` and `farthest-side`; the example demonstrates the difference as well as what it does a little bit easier:
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: radial-gradient(
	    ellipse farthest-side at 90% 90%,
	    red,
	    yellow 10%,
	    blue 50%,
	    green
	  );
}
```
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/365ei0swxnj9tcsc3wth.png)

#### closest-corner example:
This makes the gradient reach the closest corner of its container. Meaning that it will extend from the center to the point where it's closest to the center.

```CSS
  .gradient {
		background-color: purple;
		
	  background-image: radial-gradient(
	    ellipse closest-corner,
	    red,
	    yellow 10%,
	    blue 50%,
	    green
	  );
}
```
![closest-corner radial gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/c6pvfy27yxrzy60asuyz.png)

**closest-side example:**
Makes the gradient reach the closest side of its container. This means that if you're using radial-gradient as a background, it will extend from the center, to the point where it's closest to the center making it stop before it reaches the edge of the container.

Similar to `farthest-side`, the difference between the `closest-corner` and `closest-side` is more evident in an example:
```CSS
  .gradient {
		background-color: purple;

	  background-image: radial-gradient(
	    ellipse closest-side,
	    red,
	    yellow 10%,
	    blue 50%,
	    green
	  );		
}
```
![closest-side radial-gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dya2806pxpv8chqrekoq.png)


## Working with Conic Gradients
In my opinion, the most fun of the three, the conic gradient creates a gradient that rotates around a center point. Which leads to different fun effects. When used with the right colors and the right angle, it might look just like a cone (hence the name, "conic").

Like the `linear-gradient` and `radial-gradient`, they require at least two colors. A conic gradient will not accept an absolute value for the color stops, but instead degrees or percentages. Color stops are start at the top, and then progress in a clockwise direction. 

Syntax:
```CSS
conic-gradient(from <angle> at <position>, firstColor <degree>, ..., finalColor <degree>)
```
By default, the angle is set to 0deg and the position is centered. If no angle is specified, if no degree is specified in a color stop, they will be spread equally.

> **RELATED:** [⭐️  Five Underated CSS Properties You NEED to Try Out!](https://the-net-blog.netlify.app/post/five-underated-css-properties-you-need-to-try-out/)

Basic Example:
```CSS
  .gradient {
		background-color: purple;
		
	  background-image: conical-gradient(red, blue);
  }
```

![Basic conical gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/idid69kc55znn7hcbpfq.png)

### Positioning The Center of a Conic Gradient
Similar to radial gradients, you can position the center point that a gradient will rotate around using key terms, percentages, or absolute values using the keyword `at`.
```CSS
  .gradient {
		background-color: purple;
		
		  background-image: conical-gradient(at 0%, 75%, red, blue);
  }
```
![positioning center of conic gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o0blgmma4inkzyerii7c.png)
### Using Angles
`from <angle>`, specifies the starting angle by which the conic gradient will be rotated. You can also define the angle for specific color stops by including a degree after it.

```CSS
  .gradient {
		background-color: purple;
		
		background-image: conic-gradient(from 90deg, red, yellow, blue);
  }
```
![angles in conical gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/zd0ho98q8lz4hzqv0gtl.png)

In this example, we specified `from 90deg`, meaning that our gradient will run through the colors red, yellow, and blue starting at 90 degrees.
## Creating Repeating Gradients
By default, we can't repeat the color stops in a `linear-gradient`, `radial-gradient`, or `conical-gradient`. However, we have the equivalent `repeating-linear-gradient`, `repeating-radial-gradient`, and `repeating-conical-gradient` functions that do allow this type of functionality.

Repeating gradients allows us to create cool and interesting patterns using only CSS and the power of gradients.
### Repeating Linear Gradients
In the following example, we have a repeated linear gradient at 45 degrees. It starts in red, then we have another red color stop at 5px then we have a blue color stop at 5px, and a final blue color stop at 10px. The different reds and blues color stops create the repeating striped pattern.
```CSS
  .gradient {
		background-color: purple;
		
		background-image: repeating-linear-gradient(
	  	45deg, 
	  	red, 
	    red 5px,
	  	blue 5px,
	    blue 10px
  );
  }
```

![Repeating linear gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/a1t89l6q9uoswgujvrvb.png)
### Repeating Radial Gradients
Here, we have a similar example, except with a radial gradient, meaning it will expand from the center point outward, and not progress in a linear line.
```CSS
  .gradient {
		background-color: purple;
		
	  background: repeating-radial-gradient(
	    red,
	    red 5px,
	    blue 5px,
	    blue 10px
	  );
  }
```
![repeating radial gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/s36zujtqfubxgy7j9yfs.png)
### Repeating Conic Gradients
In this example, we have a repeated conic gradient that starts with red at 0 degrees (at the top of a circle) until it reaches 50 degrees. Then we have a final blue color stop that starts from blue until we reach 90 degrees. This is then repeated. 
```CSS
  .gradient {
		background-color: purple;
		
	  background: repeating-conic-gradient(
		  red 0deg 50deg,
		  blue 50deg 90deg
	  );
  }
```
![repeating conic gradients example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/jxdmwpvjf34jixmhi1kf.png)
## Advanced Techniques

### Specifying Color Positions
By default, color-stop positions will range from 0% to 100%, however, we can specify where we want to position each of our color stops using absolute values, and percentages.

```CSS
  .gradient {
		background-color: purple;
		
	  background: linear-gradient(to right, blue 16px, red, yellow 75%);
  }
```
![Color position example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/5r261c4gamfpurlglv61.png)
### Create Harsh Lines
However, we may also want to create harsh or more abrupt lines with no gradual transitioning between. In this example, where we have two colors, we have our first color stop, red, which goes through it reaches 50% of the container's height, after that, we have an abrupt change to blue with no gradual transition between the two.
```CSS
  .gradient {
		background-color: purple;
		
	  background: linear-gradient(to bottom right, red 50%, blue 50%);
  }
```
![Creating hard-lined gradients](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/72fg7lwefnselidj896w.png)
### Create Gradient Hints
Gradient hints allow you to transition from one color to another in specific percentages, or absolute values of a gradient. Here's an example comparing a default linear gradient with a gradient that has a color hint.

Gradient hint:
```CSS
  .gradient {
		background-color: purple;
		
		background-image: linear-gradient(red, 10%, blue);
  }
```
![gradient hint example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rpjug0ozbduyopf8k8rd.png)
Basic linear gradient, with no hint.
![Basic linear gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/o8zxulu6xikfuy22ui3c.png)

### Create Stacked Gradients
### Opacity and Overlays
Gradients can even be stacked on top of one another. The gradients will still be visible as long as the top ones aren't fully opaque.

This is better understood with an example:
```CSS
  .gradient {
		background-color: purple;
		
	  background:
	    linear-gradient(
	        217deg,
	        rgba(255, 0, 0, 0.8),
	        rgba(255, 0, 0, 0) 70.71%
	     ), 
	    linear-gradient(
	      127deg, 
	      rgba(0, 255, 0, 0.8),
	      rgba(0, 255, 0, 0)
	      70.71%
	    ),
	      linear-gradient(
	      336deg,
	      rgba(0, 0, 255, 0.8),
	      rgba(0, 0, 255, 0) 70.71%
	    );
  }
```

![overlaying gradient example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/hvpjbhqnspqyzxn2e2q6.png)

In this example, we're combining three different gradients to create a singular image. Our first gradient starts at 217 degrees (or a more-or-less `to bottom-left` direction), with the first color stop being red with an alpha value of 0.8. Then our second color stop is also red, except we have no alpha value (alpha values are needed to get an overlaying gradient) but instead, we specify the color stop's position to end at 70.71%. This is repeated with each gradient, with the only thing that changes being the color (the second gradient uses green, and the third one uses blue), as well as the degree of the gradient.

To understand how these are overlayed, here are the three gradients put separately:

Gradient one:
![overlaying gradient one](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/vro4zahnie3p7g7xc2vz.png)

Gradient two:
![overlaying gradient two](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/dp008a0px2dowweza217.png)

Gradient three:
![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/d0q3ucjuvcnxrrlpkorx.png)

Due to them having an alpha value, when combined we see a mixture of these three gradients.
## Online Resources
Before we end, I want to mention a few online resources that have helped me understand CSS gradients better, as well as provide some online resources that make the creation of these complicated creatures easier, if you have read through this article (which btw, I admire you if you did and appreciate it very much), you might have noticed that they might not be the most fun thing to work with.

 * The [MDN Web Docs: Using CSS Gradients](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Images/Using_CSS_gradients) have been a huge help in the creation of this article, their docs are well-written (and [open-source](https://the-net-blog.netlify.app/post/what-is-open-source/)). 
* [w3school's](https://www.w3schools.com/css/css3_gradients.asp) docs on CSS gradients are appropriate for beginners
* Both [CSS gradients](https://css-tricks.com/css3-gradients/) (Chris Coyier) and [A Complete Guide to CSS Gradients](https://css-tricks.com/a-complete-guide-to-css-gradients/) (Geoff Graham) from CSSTricks are awesome articles that are worth the read!
## Final Thoughts
This has been the longest article I've written (characters). So I help it's of much help for you to understand gradients. My idea to write an article about gradients was actually to teach web developers and designers how to effectively use gradients to enhance their users' web experience, but it kind of turned out looking kind of like a documentation : / (which btw, if you're stuck choosing colors, this article about color psychology might be the way to create effective and engaging designs and logos). 

[🏠  Home Page](https://the-net-blog.netlify.app/)

[🔥  Color Psychology for Web Developers Enhance User Experience and Engagement](https://the-net-blog.netlify.app/post/color-psychology-for-web-developers-enhance-user-experience-and-engagement/)


