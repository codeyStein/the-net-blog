+++
title = "RegExp Basics: Its Not That Bad!"
description = "While admittedly scray, RegExp is an incredibly useful tool, my goal today is for you to understand basic RegExp concepts without being overwhelmed."
date = 2023-01-15T03:00:49-06:00
tags = ['javascript', 'regexp']
draft = false
+++

![RegExp Basics: It's Not That Bad Thumbnail](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/rsmnreysa118r8kc3ey1.png)
First of all, let me apologize for the late post but I was sick this weekend and busy with
school. Now, onto the topic for today; Regular expressions in JavaScript was a topic that I always felt
scared to try. But it's something an engineer (JavaScript or not) will eventually have to touch
on, and something I never thought would be as useful as it is. My goal today is for you
to understand basic RegExp concepts without feeling overwhelmed.
<!--more-->

## Table Of Contents
1. [Introduction](#first-steps-and-why-should-i-care-about-regexp)
2. [Regexp Search Method](#regexp-string-methods)
3. [RegExp Replace Method](#regex-replace-method)
4. [RegExp Modifiers & Patterns](#regexp-modifiers-patterns)
5. [Conclusion](#conclusion)

## Introduction
Regular Expressions (regexp) in JavaScript are used to search and replace both independent characters,
or more complicated patterns. 

Before we get started with learning some basic regex methods let's first understand its syntax,
which looks something like this:
```
/pattern/modifiers
```
for example, if we have:
```
/thenetblog/g
```
then we will be doing a global search for the pattern 'thenetblog'
easy enough right?
![regexp is not that hard gif](https://media.giphy.com/media/WUay9BLLngVU3zs95c/giphy.gif)

## Regexp Search Method
As I mentioned before, regexp is commonly used to both search, and replace a pattern of text.
The `search()` method will return the position of the match (if found), else it will return `-1`.

Syntax:
`text.search(/pattern/modifiers)`

```js
let searchThis = "the best blog is The Net Blog fr"
let pattern = searchThis.search(/The Net Blog/i)
// expected return: 17

console.log(pattern)
// tip: console log is your friend when testing!

```
Good so far? Great, cause this next part is not that hard either!


> **RELATED:** [⭐️  Five USEFUL JavaScript Array Methods You MIGHT Not Know!](https://the-net-blog.netlify.app/post/five-useful-array-methods-you-might-not-know/)

## Regexp Replace method
The `replace()` method will replace the indicated pattern with a string of text.

Syntax: 

`text.replace(/pattern/modifiers, "replaced text")`


Example:
```js
let replaceThis = "The Quick Brown Fox Jumps Over The Lazy Dog"
let pattern = replaceThis.replace(/Dog/i, "Cat")

console.log(pattern)
// should return: "The Quick Brown Fox Jumps Over The Lazy Cat"

```

## RegExp Modifiers & Patterns
Patterns and Modifiers can help us perform more complicated searches, and can help us to find some
special characters that can only be searched with patterns.

### Basic Modifiers
These are some of the more basic and common modifiers
| Modifier | Description |
|----------|-------------|
| i | Preforms Case-insensitive search |
| g | Preforms Global Search |
| m | Uses `ˆ` and `$` for multiline matches |

### Patterns
Patterns can easily be identified as they are commonly placed between brackets or braces.
| Pattern | Description |
|---------|-------------|
| [xyz] | Searches for the characters placed inside the brackets |
| [0-9] | Searches for the digits placed inside the brackets |

Another important one is the `(x|y|z)` which searches for alternatives separated with the `|` character 
(Couldn't include in the table as markdown uses the same character to create tables.)

## Conclusion!
While admittedly scary at first, RegExp is an incredibly useful tool, which is not only used in JavaScript,
but other languages and software accept RegExp too!

I appreciate you spending your time reading this post, if you'd like to read more, here you go:

[🏠  Home Page](https://the-net-blog.netlify.app/)

[🔥  Configuring NeoVim with Lua: What You Should Know](https://the-net-blog.netlify.app/post/configuring-neovim-with-lua-what-you-should-know/)
