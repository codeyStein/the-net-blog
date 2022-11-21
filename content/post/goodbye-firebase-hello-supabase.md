+++
title = "Goodbye Firebase Hello Supabase"
description = "SupaBase is an open-source powerful alternative to FireBase, which offers a handful of tools aimed for web and app developers."
date = 2022-11-19T19:43:35-06:00
tags = ['database', 'tools', 'not-this-but-that']
draft = false
+++
![Goodbye Firebase, Hello SupaBase](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/0nuxzgibxeracj74wqeb.png)

Ok so we all know Firebase, a handful of tools aimed for app and web developers. Mainly used for their docuement-based database, their authentication using various social services or email and a realtime database. Supabase is a fairly new open-source alternative (unlike Firebase which is mantained by google), offer some similar tools for an afforable price too and with easy to understand and learn API.
<!--more-->
## Table Of Contents
1. [What Is SupaBase](#what-is-supabase)
2. [SupaBase's Main Features](#supabases-main-features)
3. [Similarities](#similarities)
4. [Differences](#differences)
5. [Final Thoughts](#final-thoughts)
 
## What Is SupaBase?
Supabase is an open-source alternative to FireBase. Unlike FireBase which uses a document-based database system, SupaBase uses a relational database managment system called PostSQL which allows it to be open-source, and allows you to easily do queries using SQL, comes with a handful of extensions and plugins, and it's very commonly used for transactional workloads (apps or webapps that need near-instant response queries.)

## SupaBase's Main Features
A few key features of SupaBase include:
* Storage - host images and videos with breeze,
* Auth - Easy-to-implement auth system using SQL based rule engine,
* Realtime - Any changes done in a database will be instantly change in your application,
* Edge Functions - javascript/typescript functions which deploy globally.
* Auto-Generated API which heavily improves developer expirience by allowing you to do queries from the client.,


## Similarities
They both enhance the developer expirence by making it a lot easier to create databases, you can very easily create projects straight from the browser, without any extra software or tools. Both SupaBase and FireBase provide a UI-based dashboard to manage and debug your data in realtime. The two of them also allow you to easily comunicate with your database from the client. SupaBase uses `subapase-js` which is their equivelent to the `FireBase SDK`, they can both be used on the client and on a node-js environment.

## Differences
The biggest difference between FireBase and SupaBase is probably how FireBase uses a document-based database and SupaBase uses postgresSQL they both have their own pros and cons, but there are some other pretty important differences other too like a big one for me is SupaBase is [open-source which I've explained in this article.](https://the-net-blog.netlify.app/post/what-is-open-source/), which does allow it to be hosted for free and makes it more secure. In terms of pricing FireBase charges you for reads, writes, and deletes (which has their own pros and cons), SupaBase on the other hand charges based on how much storage is used which allows for unlimited API requests and unlimited Auth users. We of course have to talk about preformance too, SupaBase did a benchmarking repo to compare their preformance versus FireBase's on which they found out SupaBase surpases FireBase by 4x on number of reads per second, and 3x on writes per second.

## Final Thoughts
SupaBase is deffenetly worth checking out and giving out a try not only your next project, but if you'd really want to you can even try to migrate from FireBase to SupaBase on an existing project. They've basiclly got everything you'll need and offer them for a good price too.

I appreciate you spending your time reading this post, if you'd like to read more here you go:

[🔥 Five Free APIs you NEED for your next project - My Last Post](https://the-net-blog.netlify.app/post/five-free-apis-you-need-for-your-next-project/)

[🏠  Home Page](https://the-net-blog.netlify.app/)

