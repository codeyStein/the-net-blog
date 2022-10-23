+++
title = "Why I chose Hugo (and why you should too)"
description = "So if you didn't know already, this website was created with Hugo, a static site generator, in this article I'll share what my experience was, pros, cons, and if you should use Hugo too."
date = 2022-10-19T17:04:07-06:00
tags = ['hugo']
draft = false
+++

Ok so, just in case you didn't know, let me explain a bit, this website was created using the static site generator: Hugo, and so far, it's working absolutely fine. In this article I'll share pros, cons, and my overall experience of Hugo, and some recommendations if you want to start using it too.
<!--more-->

## What is Hugo?

Let's start with the basics. What actually is Hugo? In short, Hugo is a fast open-source, static-site generators built with Go. Static sites are mainly used for Blogs (like this one), and documentations. In my opinion (as a software developer), it is beginner-friendly too as it has 300+ ready-to-go templates, understandable folder structure,  and it of course uses Markdown which is a pretty easy to learn markup language and A LOT better than using old plain HTML. Built with Go, it has amazing preformance time, delivering sites in less than seconds, and it allows multi languages too! While Hugo offers 300+ amazing templates, you can still *easily* create your own design.


**Hugo:**

![Hugo Is Fast](https://media.giphy.com/media/Gpu3skdN58ApO/giphy.gif)


## Hugo Compared

Now, Let's compare Hugo  with probably one of the most popular options, and compare them to Hugo

| Tech         | Built With      | Performance        |  License        |
| ------------ | --------------- | -----------------  | --------------- |
| Hugo         | Go              | 98/100 ([Full Audit](https://docs.astro.build/lighthouse/hugo/))|  Apache 2.0     |
| Astro        | TypeScript      | 92/100 ([Full Audit](https://docs.astro.build/lighthouse/astro/))|  MIT            |
| Gatsby       | React           | 46/100 ([Full Audit](https://docs.astro.build/lighthouse/gatsby/))|  MIT            |

As you can see, Hugo had the best performance score, followed by Astro, and Gatsby in last. Another thing with Gatsby is that you might get the feeling of it being way too much like actual coding, so you have less time to focus on the actual content of the article.

## Hugo's Folder Structure

Another reason why I chose Hugo is it's simple to understand folder structure or basically where all the folders are located. Here's a diagram of what a basic Hugo folder structure looks like:
```
.
├── archetypes
├── config.toml
├── content
├── data
├── layouts
├── public
├── static
└── themes
```
The main ones you are going to be using though are going to be `content` which is where all your posts will be, then inside of themes is where you are going to be placing your theme, you can either choose from the [wide gallery of Hugo themes](https://themes.gohugo.io/), or make one your own. The other file you'll be spending some time in is the `config.toml` file. This is where all the configuration of your site will be on.

## Deploying

I used [netlify](https://www.netlify.com/) to deploy my site, mainly because of how simple it was to set up, but another good option is [Github Pages](https://pages.github.com/). Both of these options allow you to have version control using GitHub.

## Final Thoughts

If you are a beginner or maybe don't even know anything about programing, then Hugo is still a perfect option to start making your blog, documentation, ect. It allows you to easily get started, and focus more on the quality of your content, while still being able to create posts easily and in a very productive maner as you only use Markdown files.
