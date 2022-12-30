+++
title = "Configuring Neovim With Lua What You Should Know"
description = ""
date = 2023-01-02T17:02:14-06:00
tags = ['productivity', 'tools', 'vim', 'neovim', 'lua', 'not-this-but-that']
draft = true
+++

## Table Of Contents
1. [Starting Out](#starting-out)
2. [Understanding the File Structure](#understanding-the-file-structure)
3. [Configuring Settings](#configuring-settings)
4. [Using and Setting Remaps](#using-and-setting-remaps)
5. [Plugins?](#plugins)
6. [Conclusion](#conclusion)

## Starting Out and Understanding the File Structure
Let's start by having a quick look at the tree of _my_ personal config.
```
.
├── after
│   └── plugin
│       ├── autopairs.lua
│       ├── cmp.lua
│       ├── dashboard.lua
│       ├── lualine.lua
│       ├── nvim-tree.lua
│       ├── telescope.lua
│       └── treesitter.lua
├── init.lua
├── lua
│   └── user
│       ├── packer.lua
│       ├── remaps.lua
│       └── settings.lua
└── plugin
    └── packer_compiled.lua

5 directories, 12 files
```
As you can see, we have 3 head directories, and one file in the parent directory. One of the most
important files will be the `init.lua` file, it's the file that NeoVim will look for on every
startup. If you have configured neovim before then it's similar to the `init.vim` file or in basic Vim your `vimrc`.

Next, we have our `after` directory which only has a `plugin` folder inside. Inside of that `plugin`
directory though, we have **all** of our configuration for our [plugins, which we'll talk aboout
later.](#plugins)

Our `lua` directory, is probably the one we'll be visiting the most. Here, inside of our personal
`user` directory, we have all of our lua files, just to break our config into different files to make it more organized.
The `packer.lua` for [our plugins (which we'll talk about later)](#plugins), the `remaps.lua` file is 
[for our remaps, which we'll configure later too](#using-and-setting-remaps), and finally our `settings.lua` file,
[where our settings are located in (we'll talk about that next).](#configuring-settings)

Just a quick note: you might notice we have a `user` directory in our `lua` directory. This can be
named anything really, some people name it after themselves, but I just preffer to keep it as
`user`. This directory however, is important as it prevents **our** lua files from interfiering with
other lua files.

You don't have to worry about the `plugin`  directory too much for now.

## Configuring Settings
Okaay so let's start by making our editor feel a little bit more comfeterable. This can easily be
done by chaning some of the editor's settings. Inside of `lua/settings.lua` or however you want to
call your settings file. To make things look a bit cleaner I made two variables to refference the
vim API. Setting up your settings is actually quite easy, the way I did it is using the following
method:

```lua
local o = vim.o

o.myOption = myValue

-- Example:
o.number = true
o.history = 50
o.mouse = 'a'
```

If you want to see more options and what they do you can use `:help options`

## Using and Setting Remaps

## Plugins

## Conclusion
**RELATED:** [⭐️ Get Started With Git: a MUST for Developers](https://the-net-blog.netlify.app/post/get-started-with-git/)

I appreciate you spending your time reading this post, if you'd like to read more here you go:

[🏠  Home Page](https://the-net-blog.netlify.app/)

[🔥 Goodbye 2022, and What to Expect in the Fututre](https://the-net-blog.netlify.app/post/goodbye-firebase-hello-supabase/)

