# Contributing to the Vault

So you want to lend your hand at making the Vault just a little bit better. Great! ...Where do you start? In [[#Quick Start Guide|Obsidian]], of course! Or maybe you just want to browse the site and interact on GitHub? You can [[Using GitHub|do that]] too.


## Quick Start Guide
If you just want to start browsing the Vault in Obsidian.

### 1. Download Obsidian
Navigate to the [Obsidian website](https://obsidian.md/download), and it should automatically detect which OS (including mobile) you're on and thereby which download you need. Download it, start it, do whatever you need to do to get it installed.

### 2. Create the vault
On the start-up screen, click "create" and follow the instructions to set a name (i usually use the same name as the repository, aka "gaylor-vault", but you can do whatever you want) and the directory to create it in. At its core, an Obsidian vault is really just a folder of markdown files, so you can put it anywhere it will let you. (on desktop at least, iOS manages it for you and I don't know about Android)

### 3. Install the Obsidian Git plugin
1. Once you have the brand new vault open, open the settings. 
	- On desktop, there is a button at the bottom left corner. It's at the top of 3, and the icon is a cog.
	- On mobile, you have to open the sidebar (button at the top left, or swipe right), then the cog button that appears.
2. Find the tab called "community plugins"
3. It'll give you a screen about security - you can read it, it gives a nice little overview. I personally have never experienced any security issues and have not heard about any from the community, so I'm not worried about it. 
>[!note] If you are concerned and you're on desktop, you can disregard most of this and set up Git outside of Obsidian (using the command line or another third-party app such as GitHub Desktop). It's definitely possible on Android but I have not tried it, and my past attempts with iOS have been unsuccessful. If you do end up doing it on mobile, let me know, I'm curious.
4. After turning on plugins, click "browse" and search for "git", it should be the first result. Install, enable it, and exit out of the modals.

### 3. Clone the repository
1. Press CTRL/CMD+P (on mobile, swipe down) to bring up the *command palette*. This is very useful, as it contains every command in Obsidian (and there's a lot!). Search for "clone" and click or press Enter on the result with "Obsidian Git:" at the beginning.
2. It asks for the remote url of the repository. Type or paste in the url "https://github.com/dykeaura/gaylor-vault.git", then make sure you click the result that's auto-filling as you type, Enter just exits the modal here for some reason.
3. It asks where you want to clone it to. Type and click "/" or click "vault root".
4. It asks if the repo has a ".obsidian" directory. This is the config folder, and currently it just has the git plugin in it (the one you're interacting with right now). Click "YES".
5. Now it asks you to confirm this is what you're trying to do - by overwriting the config directory, it's deleting itself (even though there's another copy in there). This is fine, we only had to install the plugin in the first place to get to this point. Click "DELETE ALL YOUR LOCAL CONFIG AND PLUGINS".
6. It asks for the "depth" of the clone. I don't actually know what this means, but just click the empty option that's there.
7. It starts working. Just wait until it gives you a notice to restart Obsidian, then do so.
8. Congratulations! You now have a local copy of the Gaylor Vault, with Git sync in place. Go forth and gaylor.