+++
title = "Five Underated CSS Properties You NEED to Try Out!"
description = "Helloooo! Today I'm gonna be talking about 5 CSS properties (or actually 3 properties, and 2 pseudo classes), that I think deserve more love."
date = 2022-11-28T06:59:36-06:00
tags = ['css', 'list']
draft = false
+++
Helloooo! Today I'm gonna be talking about 5 CSS properties (or actually 3 properties, and 2 pseudo classes), that I think deserve more love.
<!--more-->

## Table Of Contents
1. [accent-color](#accent-color)
2. [caret-color](#caret-color)
3. [::selection (pseudo class)](#selection-pseudo-class)
4. [user-select](#user-select)
5. [:empty (pseudo class)](#empty-pseudo-class)
6. [Final Thoughts](#final-thoughts)

## accent-color
To start of, this is a great css property just to add a little bit of more detail to your user-interface. This property applies to the input types:

* `<progress>`
* `<input type="checkbox">`
* `<input type="range">`
* `<input type="radio">`

The `accent-color` property allows you to very set the `accent` color (what you often see in radio-buttons, checkboxes, etc) to whatever color you'd like!

Example:
```css
progress {
  accent-color: red;
}

input[type=checkbox] {
  accent-color: red;
}

input[type=radio] {
  accent-color: red;
}

input[type=range] {
  accent-color: red;
}
```
![Accent Color CSS Example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/qwrkdn5uccum4p6q2j85.png)



## caret-color
While barley noticable, the `caret-color` works perfecly with the [accent-color](#accent-color) property, and is a very nice little detail you should consider adding and using.

Example:
```css
input {
  caret-color: red;
}
```

## selection (pseudo class)
While I know this is not really very *unknown*, I still don't see it used enough. The simple `::selection` pseudo element can very easily spice up your website by changing the styles of selected elements.

Example:
```css
::selection {
  background: red;
  color: white;
}
```
![Selection Pseudo Element Example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/9j27fccbfprfwwgdohf3.png)

## backdrop-filter
Like the [selection property](#selection), this might not be the most unnknown property, but I still don't see it used enough. The `backdrop-filter` property allows you to apply a variety of filters to the area behind an element.

Options:
* blur()
* brightness()
* contrast()
* drop-shadow()
* grayscale()
* hue-rotate()
* invert()
* opacity()
* sepia()
* saturate()

Example:
```css
div.background {
  background: url(image.jpg) no-repeat center;
  background-size: cover;
  height: 100px;
  width: 100px;
}

div.filterbox {
  background-color: rgba(255, 255, 255, 0.4);
  backdrop-filter: sepia(100%);
  width: 50px;
  height: 100px;
}
```
![Backdrop Filter Example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/60vkk2bx1rb5yuljf3wg.png)


## empty (pseudo class)
The `empty` pseudo class matches every element that has no children. This can be either element nodes or text (includind whitespaces). A fun usecase for this is for example when image is loading.

```css
div {
width: 60px;
height: 60px;
background: grey;
}

div:empty {
  border: 2px solid red;
}
```
![Empty Pseudo Class Example](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ranklrjrj0cuo57i9glo.png)


## Final Thoughts
That's it for today's list, there are of course there are a lot more tha I haven't mentioned, but I appreciate you spending your time reading this post, if you'd like to read more here you go:

[🔥 Goodbye Firebase, Hello SupaBase](https://the-net-blog.netlify.app/post/goodbye-firebase-hello-supabase)

[🏠  Home Page](https://the-net-blog.netlify.app/)

