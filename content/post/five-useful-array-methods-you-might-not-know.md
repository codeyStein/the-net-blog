+++
title = "Five Useful Array Methods You Might Not Know"
description = "Welcome! I don't want to spend too much time in the introduciton this time, but today I will (hopefully) teach you and show you technicly six array methods that you probably didn't know!"
date = 2022-12-10T07:09:13-06:00
tags = ['javascript', 'list']
draft = false
+++

Welcome! I don't want to spend too much time in the introduction this time, but today I will (hopefully) teach you and show you technically six array methods that you probably didn't know!
<!--more-->

## Table Of Contents
1. [concat()](#concat)
2. [some()](#some)
3. [entries()](#entries)
4. [find() and findIndex()](#find-and-findindex)
5. [copyWithin()](#copywithin)
5. [Conclusion](#conclusion)

## concat()
The `concat` array method returns a new array populated with two or more arrays merged. It does not alter any existing arrays, but rather creates a new one.

Example:
```js
const foo = [1, 2, 3';
const bar = [4, 5, 6];

const foobar = foo.concat(bar);
// expected return: [1, 2, 3, 4, 5, 6]

```

## some()
This array method tests whether or not at least one element in the array passes a test. It returns true if it finds at least one element that returns true in the provided function (callback function), else it returns false.

Example:
```js
const foobar = [7, 13, 23];

const isValid = (elm) => elm > 13

console.log(foobar.some(isValid))
// expected return: true
```

## entries()
The `entries` method returns a new Array iterator object that contains the key/value of each index of an array.

Example:
```js
const foobar = ['a', 'b', 'c']
const iterator = foobar.entries()

console.log(iterator.next().value)
// expected return: Array [0, "a"]

console.log(iterator.next().value)
// expected return: Array [1, "b"]

console.log(iterator.next().value)
// expected return: Array [2, "c"]
```

## find() and findIndex()
Returns the first element in an array that passes a test in the provided arrow function. If no element matches, then it returns `undefined`.

Example:
```js
const foobar = [10, 15, 20, 25, 30]

const test = foobar.find(elm => elm > 18)

console.log(test)
// expected return: 20
```

findIndex is very similar, but instead only returns the index, and if no element matches the test provided, then returns `-1`. The example above is expected to return `3`.

## copyWithin()
I'm not even gonna lie, I still find this one a bit confusing because of the syntax, but might be useful in some situations. This method copies array elements to another position of the same array.

syntax: `array.copyWithin(target, start, end)`

_Note that the end and start parameters are not required and if not specified, will use the first or last elements of the array._

Example:
```js
const foobar = ["a", "b", "c"]
console.log(foobar.copyWithin(2, 0, 2))
// expected return: Array ["a", "b", "a"]
```

## Conclusion
Did you know all of these? Because to be honest, I didn't either until I finished writing this article hahaha. But now that I do, I can think of plenty of situations where these might come in useful.

I appreciate you spending your time reading this post, if you'd like to read more here you go:

[🔥 STOP! Use this instead of create-react-app!](https://the-net-blog.netlify.app/post/stop-use-this-instead-of-create-react-app/)

[🏠  Home Page](https://the-net-blog.netlify.app/)
