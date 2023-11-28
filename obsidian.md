---
title: Obsidian
description: information about using Obsidian, specifically with the Vault
---

## Quick Start Guide

If you just want to start browsing the Vault in Obsidian.

### 1. Download Obsidian

Navigate to the [Obsidian website](https://obsidian.md/download), and it should automatically detect which OS (including mobile) you're on and thereby which download you need. Download it, start it, do whatever you need to do to get it installed.

### 2. Create the vault

On the start-up screen, click "create" and follow the instructions to set a name (i usually use the same name as the repository, aka "hairpinfiles", but you can do whatever you want) and the directory to create it in. At its core, an Obsidian vault is really just a folder of markdown files, so you can put it anywhere it will let you. (on desktop at least, iOS manages it for you and I don't know about Android)

### 3. Install the Obsidian Git plugin

1. Once you have the brand new vault open, open the settings.
    - On desktop, there is a button at the bottom left corner. It's at the top of 3, and the icon is a cog.
    - On mobile, you have to open the sidebar (button at the top left, or swipe right), then the cog button that appears.
2. Find the tab called "community plugins"
3. It'll give you a screen about security - you can read it, it gives a nice little overview. I personally have never experienced any security issues and have not heard about any from the community, so I'm not worried about it.
> [!note] If you are concerned and you're on desktop, you can disregard most of this and set up Git outside of Obsidian (using the command line or another third-party app such as GitHub Desktop). It's definitely possible on Android but I have not tried it, and my past attempts with iOS have been unsuccessful. If you do end up doing it on mobile, let me know, I'm curious. ^e75c2b
4. After turning on plugins, click "browse" and search for "git", it should be the first result. Install, enable it, and exit out of the modals.

### 3. Clone the repository

1. Press CTRL/CMD+P (on mobile, swipe down) to bring up the _command palette_. This is very useful, as it contains every command in Obsidian (and there's a lot!). Search for "clone" and click or press Enter on the result with "Obsidian Git:" at the beginning.
2. It asks for the remote url of the repository. Type or paste in the url `https://github.com/hairpinfiles/hairpinfiles.git`, then make sure you click the result that's auto-filling as you type, Enter just exits the modal here for some reason.
3. It asks where you want to clone it to. Type and click "/" or click "vault root".
4. It asks if the repo has a ".obsidian" directory. This is the config folder, and currently it just has the git plugin in it (the one you're interacting with right now). Click "YES".
5. Now it asks you to confirm this is what you're trying to do - by overwriting the config directory, it's deleting itself (even though there's another copy in there). This is fine, we only had to install the plugin in the first place to get to this point. Click "DELETE ALL YOUR LOCAL CONFIG AND PLUGINS".
6. It asks for the "depth" of the clone. I don't actually know what this means, but just click the empty option that's there.
7. It starts working. Just wait until it gives you a notice to restart Obsidian, then do so.
8. Congratulations! You now have a local copy of the Hairpin Files, with Git sync in place. Go forth and gaylor.

## Help Vault

If you've never used Obsidian before (or even markdown?) then I would highly recommend browsing through the Help Vault. You can find it by the little question mark button right under the settings (on desktop), or there's a published version [here](https://help.obsidian.md/Home).

## Tips for a better experience

### 1. Stay in Reading Mode as much as possible

Assuming you read at least the basics of the [[#Help Vault]], you should be able to switch between the Reading, Editing, and Live Preview modes. While Live Preview is convenient to edit with at times, I would not suggest using it as your default mode. Try to make a _deliberate_ choice to edit something, preferably after letting us know you were gonna do it. It's too easy to accidentally change something with Live Preview, and though you can [[git#Discard changes|discard those changes]] later, it's still annoying and can easily slip through if you're not careful. If they do, it's not the end of the world - just means a bit of extra work later.

> [!tip] If you often forget that you're in Live Preview like I do, turning on line numbers can help. Go to settings > Editor > Display > Show line number.

### 2. Be conservative about plugins

- Plugins attached to the Vault:
    - Obsidian Git: For Git sync purposes. Features are explored and explained in [[git|Git]].
- Aside from the [[#^e75c2b|(small) security risk]], plugins have the potential to affect the vault a lot. Try to avoid any that alter notes other than the one you have open, or if they have that option, disable/don't use it.
    - An example of this is the Linter plugin. It's pretty good at making sure notes adhere to a consistent style, and it has support for custom regex rules. But it also has commands for linting entire folders or even the whole vault. Using Linter is fine - I do, and I might add it to the Vault at some point to help keep it consistent. But absolutely do not, under any circumstances, use the mass-linting commands. If we ever do, it will be done properly and because there are a lot of files out of line with the style guidelines.
- Don't use any plugins that require special syntax that doesn't do anything when you don't have it installed
    - [Dataview](obsidian://show-plugin?id=dataview): I may end up adding it at some point as it has some very useful query functionality (obviously).
    - [Templater](obsidian://show-plugin?id=templater-obsidian): Would be quite useful when we start adding content that's not just info and how-to pages, but anything with Templater syntax on it would not get published (aka no using dynamic commands on regular pages). That's perfectly fine, since templates themselves have no place on the site anyway.
- Plugins that add convenient little quality-of-life things that don't affect other people's experiences:  
	- [Homepage](obsidian://show-plugin?id=homepage): Set it to [[index|Welcome to the Gaylor Vault!]] to get an experience more like the site! Or "random note" if you're feeling adventurous. 
	- [cMenu](obsidian://show-plugin?id=cmenu-plugin) or [Editing Toolbar](obsidian://show-plugin?id=editing-toolbar): Might be useful for people who like formatting their text and are more used to having buttons to click. I think it also has like a "focus" mode? Or maybe it's just generally minimalistic. 
	- [Advanced Tables](obsidian://show-plugin?id=table-editor-obsidian): a lifesaver when working with markdown tables, especially if you're new to markdown or it's a particularly big one (speaking from experience) 
	- [Sortable](obsidian://show-plugin?id=obsidian-sortable): Makes tables sortable like Wikipedia! There's no reason not to use this one. 
	- [Footnote Shortcut](obsidian://show-plugin?id=obsidian-footnotes) + [Better Footnotes](obsidian://show-plugin?id=better-fn): Improves the footnote experience 
	- [Folder Focus Mode](obsidian://show-plugin?id=obsidian-folder-focus-mode) + [Zoom](obsidian://show-plugin?id=obsidian-zoom): Better focus on whatever you're working on 
	- [File Explorer Note Count](obsidian://show-plugin?id=file-explorer-note-count): Not really any functional purpose, I just like having it 
	- [Reading Time](obsidian://show-plugin?id=obsidian-reading-time): Keeping an eye on the reading time for notes that other people are meant to read is always a good idea 😉 
	- [Link Favicon](obsidian://show-plugin?id=link-favicon): Icons for links. You might need to reload after enabling it. 
	- [Surfing](obsidian://show-plugin?id=surfing): Browse websites from inside Obsidian, very helpful when doing research
> [!tip] Try out some themes! Some of them are really cool. I personally use the "Dracula Gemini" theme.
