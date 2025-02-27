<h1 align="center">
  <img src="https://raw.githubusercontent.com/neovim/neovim.github.io/master/logos/neovim-logo-300x87.png" alt="Neovim">

  <p>The Wonder Of Neovim</p>
</h1>

## Table of content
- [Introduction](#introduction)
    + [So what is Neovim?](#what-is-neovim?)
    + [Why use Neovim?](#why-use-neovim?)
- [Installing Neovim](#installing-neovim)
    + [Linux](#linux)
    + [Windows](#windows)
    + [MacOS](#macos)
- [Navigation](#navigation)
    + [Basic Motion](#basic-motion)
    + [Saving and Quitting](#saving-and-quitting)
- [Plugins](#plugins)
    + [Setup lazy.nvim](#setup-lazyvim)

## Introduction

If you're reading this, you might be familiar with code editor like Visual Studio Code, Sublime or IDEs like Dev C++, Pycharm,... They all have one thing in common is that they are resource-heavy and bloated. Sure some of them are indeed light-weight and some are heavy because of built-in features in them, but what if I told you Neovim can do the same thing but better and faster?

### So What Is Neovim?

Neovim is a highly extensible keyboard-based editor on terminal-based where your mouse is almost completely useless, and because of that, it can can improve your productivity since you won't need to touch the mouse. Neovim originally came from Vim or Vi and also a drop-in replacement of it, meaning Neovim are 99% identical to Vim but most of it's code base are refactored to be better, this also help the community to make faster and stronger plugins for Neovim.

### Why use Neovim?

Here are **3 reasons** why I pick Neovim for my daily coding editor:

1. It's insanely fast in navigation and minimalist workflow.
2. The Neovim customization is beyond your own limits (or someone else plugins/config).
3. Neovim is light-weight which can be run in everywhere (especially server).

## Installing Neovim

So you're here because you don't know how to install it or you did it but it's somehow broken or not working properly.

### Linux

Neovim exist in almost Linux distributions repositories due to its popularity so most likely you can install it using your distrubution's package manager.

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

(image later)

You may think: __"How can this post claim Neovim outperforms my current editor, I literally can't even type!, how can I move around?, I can't do anything! **HOW DO I EXIT THIS?!?!?**"__.

That's because you haven't set everything up so it's can usable. Neovim becomes powerful when you learn how to use it and invest time customizing or install plugins to it.
### Basic Motion

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

**Command-line** Mode (For Command)** 
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

### Saving and quitting

To quit a file simply enter command mode then type `wq`

- `w` stands for saving a file.
- `q` stands for quitting a file.

So if you want to save or quit then use only one of them in command mode.

##### And this is almost every basic Neovim motion, it might hard at first that you cannot remember all of the keybinds but you can always learn to use it effectively but for now pick some that you think you will use the most and goes on till you master it. Also you can use `:help` to help you understand more about some about vim.

## Plugins

Now this one might be the most fun part because now you will try to install plugins into it to make it more powerfull.

### Setup lazy.nvim

Lazy.nvim is a modern neovim plugin manager. It's provide you with powerful UI to manage plugins and fast startup time when you installed a lots of plugin. Of course there are many more plugin manager like Packer, vim-plug but I'm too lazy to manually set those up and if you like me then this plugin manager is for you also.

#### Requirements

- Neovim >= 0.8.0 (needs to be built with LuaJIT)
- Git >= 2.19.0 (for partial clones support) 
- a [Nerd Font](https://www.nerdfonts.com/) (optional)

#### Installation

First you need to locate where your Neovim configuration is locate

- For Linux simply go to `~/.config/nvim`.
- For Windows go to `Appdata/Local/nvim`. Or go into nvim then use `:echo stdpath('config')` to locate nvim folder.
- For MacOS, it's basically the same for Linux `~/config/nvim`.

If it didn't exist then create a folder name `nvim` in your config directory and inside make a file name `init.lua`.

You can setup a structured system but I'm lazy to do that so here we will do it in a single file.

Paste this into your Neovim config file: 

```lua
-- Bootstrap lazy.nvim
local lazypath = vim.fn.stdpath("data") .. "/lazy/lazy.nvim"
if not (vim.uv or vim.loop).fs_stat(lazypath) then
  local lazyrepo = "https://github.com/folke/lazy.nvim.git"
  local out = vim.fn.system({ "git", "clone", "--filter=blob:none", "--branch=stable", lazyrepo, lazypath })
  if vim.v.shell_error ~= 0 then
    vim.api.nvim_echo({
      { "Failed to clone lazy.nvim:\n", "ErrorMsg" },
      { out, "WarningMsg" },
      { "\nPress any key to exit..." },
    }, true, {})
    vim.fn.getchar()
    os.exit(1)
  end
end
vim.opt.rtp:prepend(lazypath)

-- Make sure to setup `mapleader` and `maplocalleader` before
-- loading lazy.nvim so that mappings are correct.
-- This is also a good place to setup other settings (vim.opt)
vim.g.mapleader = " "
vim.g.maplocalleader = "\\"

-- Setup lazy.nvim
require("lazy").setup({
  spec = {
    -- add your plugins here
  },
  -- Configure any other settings here. See the documentation for more details.
  -- colorscheme that will be used when installing plugins.
  install = { colorscheme = { "habamax" } },
  -- automatically check for plugin updates
  checker = { enabled = true },
})
```

# Mastering Neovim: A Beginner's Guide

Neovim is a powerful, modernized version of Vim that offers extensive customization and efficiency. If you're new to Neovim, this guide will help you get started by covering its basic modes, navigation, editing commands, and even plugin management.

---

## Opening a File in Neovim
To open a file with Neovim, use the following command:
```sh
nvim <file-name>
```

If the file doesn't exist, Neovim will create a new one upon saving.

---

## Understanding Neovim's Modes
Neovim has four primary modes:

### 1. **NORMAL Mode** (Default Mode)
   - Used for navigation and executing commands.
   - Press `<ESC>` to return to this mode from other modes.

### 2. **INSERT Mode** (Typing Mode)
   - Allows you to type text like a traditional editor.
   - Press `i` to enter INSERT mode.

### 3. **VISUAL Mode** (Selection Mode)
   - Used for selecting text.
   - Press `v` to start selection.
   - Press `V` to select entire lines.

### 4. **COMMAND-LINE Mode** (For Commands)
   - Accessed by pressing `:`.
   - Used for commands like saving and quitting.

---

## Navigation in NORMAL Mode
### **Basic Movements**
- `h` → Move cursor **left**
- `l` → Move cursor **right**
- `j` → Move cursor **down**
- `k` → Move cursor **up**

### **Vertical Movements**
- `Ctrl + u` → Move **up** half a page
- `Ctrl + d` → Move **down** half a page
- `G` → Jump to the **bottom** of the file
- `gg` → Jump to the **top** of the file
- `{` → Move **up** by paragraph
- `}` → Move **down** by paragraph

### **Searching**
- `/word` → Search **forward** for "word"
- `?word` → Search **backward** for "word"
- `n` → Jump to the **next** match
- `N` → Jump to the **previous** match
- `*` → Search for the **word under the cursor** forward
- `#` → Search for the **word under the cursor** backward

### **Horizontal Movements**
- `w` → Jump **forward** to the start of the next word
- `e` → Jump **forward** to the end of the current/next word
- `b` → Jump **backward** to the start of the previous word
- `f<char>` → Jump to the next occurrence of `<char>` in the current line
- `F<char>` → Jump to the previous occurrence of `<char>` in the current line
- `;` → Repeat the last `f` or `F` search
- `,` → Repeat the last `f` or `F` search in reverse
- `$` → Jump to the **end** of the line
- `0` → Jump to the **beginning** of the line

---

## Editing Commands
- `d` → Delete selected text
- `dd` → Delete the current line
- `y` → Yank (copy) selected text
- `yy` → Yank the current line
- `p` → Paste after the cursor

---

## Saving and Quitting
- `:w` → Save the file
- `:q` → Quit Neovim
- `:wq` or `ZZ` → Save and quit
- `:q!` → Quit without saving

---

## Exploring Neovim Plugins
One of the best aspects of Neovim is its extensibility through plugins. A plugin manager makes it easier to install and manage plugins.

### **Setting Up `lazy.nvim`**
`lazy.nvim` is a modern Neovim plugin manager that provides a powerful UI for managing plugins while ensuring fast startup times. There are other options like `Packer` and `vim-plug`, but `lazy.nvim` is easier to set up.

To install `lazy.nvim`, follow these steps:
1. Open Neovim and run the following command to install `lazy.nvim`:
   ```sh
   git clone --filter=blob:none https://github.com/folke/lazy.nvim.git \
       --branch=stable ~/.local/share/nvim/lazy.nvim
   ```
2. Then, configure it inside your Neovim config (`init.lua`).

---

## Conclusion
Mastering Neovim takes time, but starting with basic navigation and editing commands will make your workflow more efficient. Pick a few key bindings that feel most useful and build from there. And remember, Neovim has built-in documentation—just type `:help` for more details.

Happy coding!

