<h1 align="center">
  <img src="./assets/Neovim_logo.png" alt="Neovim">

  <p>Neovim The Editor</p>
</h1>

## TABLE OF CONTENT
- [Introduction](#introduction)
    + [So what is Neovim?](#what-is-neovim)
    + [Why use Neovim?](#why-use-neovim?)
    + [What is Neovim capable of?](#what-is-neovim-capable-of)
- [Installing Neovim](#installing-neovim)
    + [Linux](#linux)
    + [Windows](#windows)
    + [MacOS](#macos)
- [Navigation](#navigation)
    + [Basic Motion](#basic-motion)
    + [Saving and Quitting](#saving-and-quitting)
    + [Macros](#macros)
- [Plugins](#plugins)
- [Conclusion](#conclusion)

## Introduction

If you're reading this, you might be familiar with code editor like Visual Studio Code, Sublime or IDEs like Dev C++, Pycharm,... They all have one thing in common is that they are resource-heavy and bloated. Sure some of them are indeed light-weight and some are heavy because of built-in features in them, but what if I told you Neovim can do the same thing but better and faster?

### So what Is Neovim?

Neovim is a highly extensible keyboard-based editor on terminal-based where your mouse is almost completely useless, and because of that, it can can improve your productivity since you won't need to touch the mouse. Neovim originally came from Vim or Vi and also a drop-in replacement of it, meaning Neovim are 99% identical to Vim but most of it's code base are refactored to be better, this also help the community to make faster and stronger plugins for Neovim.

### Why use Neovim?

Here are **3 reasons** why I pick Neovim for my daily coding editor:

1. It's workflow is smooth because of the Neovim motion.
2. The Neovim customization is beyond your own limits (or someone else plugins/config).
3. Neovim is light-weight which can be run in everywhere (especially server).

### What is Neovim capable of?

To be honest Neovim can be use to write anything you want not just coding. You can write diary, note, plan, etc and with plugins, you can improve the experience of writing which we will cover in the last section.

Most of the time I use Neovim for coding because how fast and strong it is and sometime I use Neovim for writing like the one you reading right now. But you can see Neovim as a empty Notebook, a Journal or even just a paper.

## Installing Neovim

Enough with the introduction, now we will install Neovim into our system.

### Linux

Neovim exist in almost Linux distributions repositories due to its popularity so most likely you can install it using your distribution's package manager.

1. Arch (btw)

```
$ sudo pacman -S neovim
```

2. Ubuntu/Debian

```
$ sudo apt install neovim
```

3. Fedora

```
$ sudo dnf install -y neovim python3-neovim
```

### Windows

If you using windows especially windows 11 then `winget` (A package manager for windows) already installed in your computer. Simply use this command to install.

```
winget install Neovim.Neovim
```

There's also alternative package manager for windows like Scoop or Chocolatey and if you using any of it, use these command

1. Scoop
```
scoop bucket add main
scoop install neovim
```

2. Chocolatey

```
choco install neovim
```

If you use neither of those then you can visit [Neovim official repo](https://github.com/neovim/neovim/releases/tag/v0.10.4) and look for `nvim-win64.msi`
### MacOS

If you using homebrew (which you should be), you can install Neovim with the following command:

```
brew install neovim
```

## Navigation

When you first open up Neovim and what first pop up is: 

![First Start](./assets/first_start.png)

You may think: __"How can this post claim Neovim outperforms my current editor, I literally can't even type!, how can I move around?, I can't do anything! **HOW DO I EXIT THIS?!?!?**"__.

That's because you haven't set everything up so it's can usable. Neovim becomes powerful when you learn how to use it and invest time customizing or install plugins to it.
### Basic Motion

Unlike any editors, you have to use your mouse or arrow keys to move the cursor. Here in Neovim, you can move around using the keyboard thus improve your speed. So in this section, we will cover the basic motion of Neovim.

First to open a file with Neovim use the following command: 

```
nvim <file_name>
```

If the file doesn't exist then Neovim will create a new one upon saving.

There are 4 main modes in Neovim: 

**NORMAL Mode (Default Mode)**
- Used for navigating and executing commands.
- Press `<ESC>` to return to this mode from other modes.

**INSERT Mode (Typing Mode)**
- Allows you to type like a normal editor.
- Press `i` to enter INSERT mode.

**VISUAL Mode (Selection Mode)**
- Used to select texts.
- Press `v` for selection.
- Press `V` for select entire line.

**Command-line Mode (For Command)**
- Press `:` to enter this mode.
- Used for command like saving and quitting.


Now we'll move on to Navigation or how to move around in **NORMAL** mode.

**Basic movements:** 

- `h` → Move left
- `l` → Move right
- `j` → Move down
- `k` → Move up

**Vertical movement:**

- `Ctrl + u` → Move **up** half a page
- `Ctrl + d` → Move **down** half a page
- `G` → Jump to the **bottom** of the file
- `gg` → Jump to the **top** of the file
- `{` → Move **up** by paragraph
- `}` → Move **down** by paragraph

**Searching**

- `/word` → Search **forward** for "word"
- `?word` → Search **backward** for "word"
- `n` → Jump to the **next** match
- `N` → Jump to the **previous** match
- `*` → Search for the **word under the cursor** forward
- `#` → Search for the **word under the cursor** backward

**Horizontal movements:**

- `w` → Jump **forward** to the start of the next word
- `e` → Jump **forward** to the end of the current/next word
- `b` → Jump **backward** to the start of the previous word
- `f<char>` → Jump to the next occurrence of `<char>` in the current line
- `F<char>` → Jump to the previous occurrence of `<char>` in the current line
- `;` → Repeat the last `f` or `F` search
- `,` → Repeat the last `f` or `F` search in reverse
- `$` → Jump to the **end** of the line
- `0` → Jump to the **beginning** of the line

**Editing Commands**
- `d` → Delete selected text
- `dd` → Delete the current line
- `y` → Yank (copy) selected text
- `yy` → Yank the current line
- `p` → Paste after the cursor

**Saving and Quitting**
- `:w` → Save the file
- `:q` → Quit Neovim
- `:wq` or `ZZ` → Save and quit
- `:q!` → Quit without saving

#### Example

```ts
interface User {
  name: string;
  id: number;
}
 
class UserAccount {
  name: string;
  id: number;
 
  constructor(name: string, id: number) {
    this.name = name;
    this.id = id;
  }
}
 
const user: User = new UserAccount("Murphy", 1);
```
I have this example Typescipt code and I want to change `"Murphy"` into something else. The most simple way to this is use `G` to go the last line then `fM` to move into the string and press `de` to delete the current word, next edit it to something ese.

![Demo GIF](./assets/demo.gif)

### Saving and quitting

To quit a file simply enter command mode then type `wq`

- `w` stands for saving a file.
- `q` stands for quitting a file.

So if you want to save or quit then use only one of them in command mode.

**Macros**

Macros or Record and Playbacks is a command can help you repeats the complex changes by recording it. This command is really good for repetitive task because having macros for it can save you time. There are 3 step to make a Macro

1. press `q{register}` to start recording (The register name is range from a to z).
2. type your commands
3. Press `q` to stop the record.

Now you can execute the Macros by typing the command `@{register}`.

**EXAMPLE**

We have these Library in Typescript and I want to change it to ES6 import 

```ts
const express = require("express")
const path = require("path")
const fs = require("fs")
```

We can do this with these following commands:

`qt` to start recording.\
`_` Move to beginning of the line.\
`de` remove the `const`\
`iimport<ESC>` Insert the string `import` at beginning of the line.\
`f=` Move to `=` sign.\
`df(` Remove from `=` to `(`.\
`ifrom <ESC>` Insert string `from`.\
`$` Move to the end of the line.\
`a <DEL><ESC>` Remove the last `)`.\
`j` Move to the next line.\
`q` Stop recording the macro.

So now we got a macro that can change to import ES6, you can repeat the change by typing the command `@t` 3 times or `3@t` to make it execute 3 times.


##### And this is almost every basic Neovim motion, it might hard at first that you cannot remember all of the keybinds but you can always learn to use it effectively but for now pick some that you think you will use the most and goes on till you master it. Also you can use `:help` to help you understand more about some about vim.

## Plugins

Now this one might be the most fun part because now you will try to install plugins into it to make it more powerful. To make things easier, we will use a Neovim distro called kickstart.nvim. Unlike others distro where they did everything for you, this one only install the bare minimum for it like a package manager, LSP server,..., and some pre-configuration.

#### Requirements

- Neovim >= 0.8.0 (needs to be built with LuaJIT)
- Git >= 2.19.0 (for partial clones support) 
- a [Nerd Font](https://www.nerdfonts.com/) (optional but recommend for better experience)

#### Installation

First you need to locate where your Neovim configuration is locate

- For Linux simply go to `~/.config/nvim`.
- For Windows go to `Appdata/Local/nvim`. Or `%localappdata%\nvim\`
- For MacOS, it's basically the same for Linux `~/config/nvim`.

If it not exist, create one your own.

The recommended way to install Kickstart.nvim is to fork one your own from this [link](https://github.com/nvim-lua/kickstart.nvim) then install it by cloning the fork to your nvim folder by using this command below.

**Linux/Mac**

```sh
git clone https://github.com/nvim-lua/kickstart.nvim.git "${XDG_CONFIG_HOME:-$HOME/.config}"/nvim 
```

**Windows**


If you use `cmd.exe`
```
git clone https://github.com/nvim-lua/kickstart.nvim.git "%localappdata%\nvim"
```

If you use `powershell.exe`
```
git clone https://github.com/nvim-lua/kickstart.nvim.git "${env:LOCALAPPDATA}\nvim"
```

After you installed it Lazy.nvim (a package manager) will install all the plugins you have. Use `:Lazy` to view all the plugins status. Hit `q` to close the window.

| ![Lazy.nvim](./assets/lazynvim_example.png) |
|:--:| 
| *Lazy.nvim Example* |

Then you should briefly read the Friendly Document in `init.lua` from you nvim config folder to further understand about Neovim configuration.


Kickstart.nvim already setup for LSP server or IntelliSense you normally see in VS code and other IDE.

For example: To install new LSP like Python use command `:Mason` it'll have a popup that contain available LSP.

![Mason](./assets/mason.png)

Then press `Ctrl + f` to filter out languages and find Python.

![Mason Find Python](./assets/mason_find_python.png)

There're lots of LSP here but scroll down a bit and you'll see one called python-lsp-server.

![Mason Install Python](./assets/mason_intstall_python.png)

Then press `i` to install it. After that Python should appear here.

![Mason Post Install](./assets/mason_post_install.png)

Now whenever you open a python file the LSP should work out of the box like this:

![Python file](./assets/python_file.png)

Right now Neovim should work like a charm with autocomplete and suggestion but if you want to extend even more, you can visit this [github repo](https://github.com/rockerBOO/awesome-neovim) to find your favorite plugins

Also here are my list of current plugins I currently use: 

- ['numToStr/Comment.nvim'](https://github.com/numToStr/Comment.nvim)
- ['stevearc/oil.nvim'](https://github.com/stevearc/oil.nvim)
- ['windwp/nvim-autopairs'](https://github.com/windwp/nvim-autopairs)
- ['tribela/transparent.nvim'](https://github.com/tribela/transparent.nvim)
- ['folke/twilight.nvim'](https://github.com/folke/twilight.nvim)
- ['folke/zen-mode.nvim'](https://github.com/folke/zen-mode.nvim)
- ['ThePrimeagen/vim-be-good'](https://github.com/ThePrimeagen/vim-be-good)

If you read the Friendly Document then you should know where to put plugins so Lazy could install it. In case you don't, use search and find `require('lazy')` or just `lazy`. 

### Conclusion

Neovim is indeed a strong tool for your writing but only you actually thinking about using it right. If you don't feel like it you can still use your favorite code editors or IDEs but it is a thing that you should try at least once especially you're in IT field because I, myself learnt a lots of how things work under the hood when trying it. Lasty Neovim is not all about speed but it about the flow when we write.

### Source

[Neovim Docs](https://neovim.io/doc/user/)

