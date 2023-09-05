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
You think of a commit as a snapshot in time - you can (temporarily) teleport to any one of them and see what a note was like then. Really, it's just a set of diffs, and what you see is the result of all the diffs of the commits in that file's history compiled together. 
