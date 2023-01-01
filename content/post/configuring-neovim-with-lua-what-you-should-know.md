+++
title = "Configuring Neovim With Lua: What You Should Know"
description = "NeoVim is such an amazing and powerful tool. It's insanely fast, flexible, and clean. In today's article, I'm going to show you how to get started on making your neovim config!"
date = 2023-01-02T17:02:14-06:00
tags = ['productivity', 'tools', 'vim', 'neovim', 'lua', 'not-this-but-that']
draft = false
+++

[Configuring Neovim With Lua: What You Should Know](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/tz4474zp86nwj5tg9lwd.png)
NeoVim is such an amazing and powerful tool. It's insanely fast, flexible, and clean. I honestly can't
believe I used to use vimscript to set it up, but anyways, in today's article, I'm going to show you how to
start making your neovim config! But before we continue though, I'd like to give a big shout-out to
[Chris@machine's NeoVim from Scratch series](https://github.com/LunarVim/Neovim-from-scratch), and
[ThePrimeagen](https://github.com/ThePrimeagen/init.lua), since a lot of my config is based on theirs.
<!--more-->

## Table Of Contents
1. [But Why](#but-why)
2. [Starting](#starting)
3. [Configuring Settings ](#configuring-settings)
4. [Using and Setting Remaps](#using-and-setting-remaps)
5. [Plugins?](#plugins)
6. [Conclusion](#conclusion)

## But why?
Before we get started, you must understand why pairing NeoVim with Lua will make such a big
difference. Here are some key points of why using Lua is more beneficial than vimscript:
* Organisation - NeoVim allows you to use a more clean-looking file Structure.
* Faster - Lua is a **lot** faster than vimscript
* Plugins - Specifically talking about Packer here, it makes making amazing plugins easier.
* It's Lua - Let me justify a bit, vimscript is a scripting language, specifically made to configure Vim. On the other hand, Lua is an actual programing language, which allows the editor to do so many more amazing things!

And don't worry, vimscript can still be used if it is needed, which I'm going talk a little about
[here.](#starting-out-and-understanding-the-file-structure)

## Starting
First, I'd recommend you make sure to have the latest version of NeoVim installed. You can get the
latets on their [releases page.](https://github.com/neovim/neovim/releases) Let's start by having 
a quick look at the tree of _my_ personal config tree.
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
As you can see, we have three head directories and one file in the parent directory. One of the most
important files will be the `init.lua` file; it's the file that NeoVim will look for on every
startup. If you have configured neovim before, it's similar to the `init.vim` file or `vimrc` in
Vim. You must remember to `require` each file you want to use in the `lua/user` directory.

Next, we have our `after` directory, which only has a `plugin` folder inside. Inside that `plugin`
directory, we have **all** of our configuration for our [plugins, which we'll talk about
later.](#plugins)

Our `lua` directory, is probably the one we'll be visiting the most. Here, inside our personal `user` directory
we've split all our Lua files. The `packer.lua`  [our plugins (which we'll talk about later)](#plugins), the `remaps.lua`
file is [for our remaps, which we'll configure later too](#using-and-setting-remaps), and finally, our `settings.lua` file,
[where our settings are at (we'll talk about that next).](#configuring-settings)

Just a quick note: you might notice we have a `user` directory in our `lua` directory. This can be
named anything, some people name it after themselves, but I prefer to keep it as
`user`. This directory, however, is important as it prevents **our** Lua files from interfering with
other Lua files.

You don't have to worry about the `plugin`  directory too much for now.

I wanted to address quickly: you can still use vimscript if you really need by
using `vim.cmd[]`,
```vimscript
vim.cmd [[
  # vim script goes here!
  syntax enable
]]

```

## Configuring Settings
Let's start by making our editor feel a little bit more comfortable. This can easily be
done by changing some of the editor's settings. Inside of `lua/settings.lua` or however you want to
call your settings file. To make things look cleaner, I made two variables to reference the
vim API. Setting up your settings is easy; the way I did it is using the following
method:

```lua
local o = vim.o

o.myOption = myValue

-- Example:
o.number = true
o.history = 50
o.mouse = 'a'
```

On the examples above I used the scope for general settings, but of course, there are many more:
* `vim.o` - for general settings
* `vim.wo` - for for window-scoped options.
* `vim.bo` - for for buffer-scoped settings.
* `vim.g` - for for global variables, which you're commonly use for plugins.
* `vim.opt` - to set global, window, and buffer options. Basiclly `:set`

If you want to see more options and what they change to the edtior, you can use `:help options`

## Using and Setting Remaps
Remaps, while you can live without them, definitely make the developer experience a lot
more comfortable, and sometimes can even boost productivity. They are also easy to set up.
So In our remaps.lua file inside of `lua/user` we'll do:

* Mode - refers to what mode the remap is for. You're gonna have to use an abreviation though, which
you can find the list of [here.](https://github.com/nanotee/nvim-lua-guide#defining-mappings)
* Function - can be either a command from the bar, or a key combination (in the same format you
        define the remap)
* For additional arguments, you might want to use `:help vim.keymap.set()`.
```lua
-- Some variables to be more organized
local opts = { noremap = true, silent = true } -- Commonly used option
local keymap = vim.api.nvim_set_keymap -- Calls the vim api

-- Basic Syntax:
keymap("mode", "<remap>", "function") -- more info about what these mean above.

-- Example:
keymap("n", "<C-e>", ":NvimTreeToggle<cr>", opts)
--     ^^^ will run ":NvimTreeToggle", which is a plugin that I'll talk about later

```
To get an idea of some remaps you might like, you can check out [my personal remap file](https://github.com/codeyStein/cozy-apple/blob/master/nvim/lua/user/remaps.lua)

**RELATED:** [⭐️ Get Started With Git: a MUST for Developers](https://the-net-blog.netlify.app/post/get-started-with-git/)
## Plugins
Plugins are a big part of neovim (and honestly one of my favorites) because they make it so easy
to use Lua to make plugins, which allows the community to create amazing plugins! While there are
multiple plugin managers available, I found I liked [packer.nvim](https://github.com/wbthomason/packer.nvim)
the most. To get started you need a `packer.lua` file. In this file, we'll first install Packer, and
then I added some other optional commands [(thanks to chris@machine)](https://github.com/LunarVim/Neovim-from-scratch), 
like making Packer use a popup window. If we move a little further down, we'll see some of the
actual plugins. To install plugins you can use the following:
```lua
-- Simple syntax:
use "github/repo"

-- For more options:
use({
        'github/repo',
        -- other options, but I'd recommend using a separate config file for each plugin
})

-- Example:
use({'nvim-treesitter/nvim-treesitter', run = ':TSUpdate'})
-- ^^^ Installs nvim-treesitter, and runs ':TSUpdate' on load
```

Again, you can check out [my config](https://github.com/codeyStein/cozy-apple/blob/master/nvim/lua/user/packer.lua) to get an idea of the plugins that I use.
But here are some of my personal favorites:
* [treesitter](https://github.com/tree-sitter/tree-sitter) - Better syntax highlighting,
* [gruvbox](https://github.com/ellisonleao/gruvbox.nvim) - my color scheme
* [telescope](https://github.com/nvim-telescope/telescope.nvim) - fuzzy finder


Most plugins require, or you'll most likely want to configure them. Now, you can configure your
plugins in the `packer.lua` file, but I'd recommend creating a separate file for each plugins you
want to configure in `after/plugin`. The first thing you'll have to do in every configure file is
require your plugin, then you can simply follow the docs of each specific plugin. Here are my 
[plugin config files](https://github.com/codeyStein/cozy-apple/tree/master/nvim/after/plugin), which again
are heavily inspired from [NeoVim from Scratch.](https://github.com/LunarVim/Neovim-from-scratch)

## Conclusion
I hope that you learnt at least one thing new while reading today. In short, we've learnt the basics
of how to define new remaps, set settings, and use a plugin manager to use.. well plugins!

I appreciate you spending your time reading this post, if you'd like to read more here you go:

[🏠  Home Page](https://the-net-blog.netlify.app/)

[🔥 Goodbye 2022, and What to Expect in the Fututre](https://the-net-blog.netlify.app/post/goodbye-firebase-hello-supabase/)

