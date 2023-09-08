# Using Git

Git can feel a little intimidating to learn, but it's not actually that complicated (I know that's what everyone says and it's not always true but I promise you can handle it).

## Overview
Git is what's known as a *version control system* (VCS), a program for tracking and managing changes to files. If you've used the versioning tools from Dropbox or Google Drive, congratulations! You already have experience with a rudimentary form of a VCS. Git, though, was made for teams of developers with a lot of changes happening at once - that would be pretty difficult to manage with a more straightforward tool.

Rather than storing a whole copy of a file for every change, it only keeps track of the changes themselves (at least for text files -more on that later). This reduces the size of the repository by a lot, and enables the use of some more advanced commands.

Each change is either an *addition*, *deletion/removal*, or *modification.* This applies on a file level and on an individual line level. When a file is added or removed, all of its lines were also added or removed, respectfully. In a modified file, its lines could be any combination of added, removed, modified, or unchanged. Here, a line being modified is really just an addition on top of a removal. This changes are also called *diffs*. Most programs that offer Git management offer a *diff view*, including the Obsidian Git plugin we have installed on the Vault. Pull up the command palette (CTRL/CMD+P) and search for "source", and it should come up with a "source control view". Click it, and it will open in the right side panel (you can move it anywhere you want, of course).

You should now be presented with this view:
![[source_control_view.png]]
There's a lot here - don't worry, we'll go through it all slowly. For right now, you may notice that you don't have anything listed under "changes". That's fine - good, actually. It just means you've been good and not changed anything. 😉 But now you do need to change something: go into Editing Mode (or Live Preview) and change something on this page, anything. (maybe make it something you already read, though) Wait a few seconds, or press the "refresh" button (the circular arrows). "Using Git" (the page you're on right now, in case you forgot) should now appear there under the changes. If you click it, it'll switch to a diff view of the page. Your changes are highlighted in green, red, and/or a yellowish-brown colour. With modified lines, it shows you what part of the line actually changed - that's just a cosmetic thing the plugin does for readability, Git keeps track of whole lines only.

## Commits
You think of a commit as a snapshot in time - you can (temporarily) teleport to any one of them and see what a note was like then. Really, it's just a set of diffs, and what you see is the result of all the diffs of the commits in that file's history compiled together. A commit is identified by its *commit hash* - a long string of letters and numbers, like this one: **d405a2b0cfc05b8dddd7bb47df462c5058da070e**. They're often referred to only by the first eight characters, because the chance of duplicates is extremely low. They also have a *parent commit* (or 2, in the case of [[#Merge|Merge Commits]]), which is the commit that came before it. By following this all the way through, you can construct the commit history, and the visualizations of them is what people typically think of when they think of Git. 
>[!note] The plugin we're using doesn't have a "graph view", but you can view it on the [GitHub repository.](https://github.com/dykeaura/gaylor-vault/network) It's not a pretty one - GitHub sort of dropped the ball on this feature specifically, because every other Git provider has a nice graph view, and this is the closest we get with GitHub. If you want a nice fancy one, you're gonna have to find some some other app to do that, unfortunately. The GitHub one includes [[Using GitHub#Forks|Forks]] though, so that's nice.

### Commit Messages
When you create a commit, you'll supply a message to describe the changes in it. Technically there's no right or wrong way to do this, but here are some tips:
- Be descriptive, but still short and sweet. This matters less for us than it does for an actual codebase, because we don't have bugs that we have to fix by hunting down when they were introduced. But it still helps with other things, like reviewing [[Using GitHub#Pull Requests|Pull Requests]].
- You can have multiple lines - the first line will be used as the "title", and if you put a blank line after it, then a paragraph, it will be used as the "body" or description.
	- Try and keep the title under 50 characters and the body under 72.
- If you mention an [[Using GitHub#Issues|Issue]], GitHub will pick up on it and it will be linked. That's not super helpful, but if you preface it with any of the words "close", "closes", "closed", "fixes", or "fixed", the issue will be closed automatically when the commit is eventually [[#Merging|Merged]] in to `master` (the main [[#Branches|Branch]]).
- Use *imperative mood*, like "fix typo", or "add page about Big Sur". Admittedly, I haven't been very good about doing this, but it's convention and aligns with what Git uses for [[#Merging]] and reverts (if you're curious about that, look it up yourself and get comfortable with it somewhere else please).
	- You're also supposed to keep the title as one statement and not end with punctuation. (pretty sure I've already broken the first rule, oops)
- I don't really care about the first letter being capitalized, but try to keep the rest of the message as readable as possible. Avoid obscure abbreviations and acronyms.

### Staging
Below the commit message box, there are 2 sections: staged changes and (unstaged) changes. To stage a change, click the plus to the right of the file name, or unstage it by clicking the minus. Staging a change means to *include it in the next commit*. If you go a long time without committing (which I wouldn't recommend), you may end up with a lot of changes here, and you can split them up by staging only some before committing, then doing the others after (or continuing to edit). Git actually allows staging each line individually, but I'm not sure how to do that with this plugin, or if you even can.

### Discarding changes
If you click the backwards arrow button next to the "stage" button, you can *discard* all changes to a file and reset it back to the last commit . Useful for reverting changes you didn't mean to make, especially if you don't know or remember what it was like before. Of course, this can be quite destructive, so be careful.

## Remotes
A remote is a reference to another Git repository somewhere, usually an online Git provider like GitHub, GitLab, or Bitbucket. When you [[#Cloning|cloned]] the Vault, it automatically added the url of our GitHub repository as a remote called "origin", which is convention for the main remote.
>[!note] The url always needs to have ".git" at the end. To get the proper https url of a GitHub project just use `https://github.com/{user or organization}/{repository name}.git`.

## Push and Pull
Pushing and pulling are the actions of sending and receiving new [[#Commits]] from the [[#Remotes|Remote]]. The 