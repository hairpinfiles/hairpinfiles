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

You can create a commit by [[#Staging]] changes, entering a [[#Commit Messages|Commit message]], then pressing the commit button. (the checkmark) If you press the circled up arrow ("backup"), it will commit and immediately [[#Push and Pull|Push]].

A commit is identified by its *commit hash* - a long string of letters and numbers, like this one: **d405a2b0cfc05b8dddd7bb47df462c5058da070e**. They're often referred to only by the first eight characters, because the chance of duplicates is extremely low. They also have a *parent commit* (or 2, in the case of [[#Merge|Merge Commits]]), which is the commit that came before it.

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
>[!tip] There are also "stage all" and "unstage all" buttons, the circled plus and minus beside the commit button.

### Discarding changes
If you click the backwards arrow button next to the "stage" button, you can *discard* all changes to a file and reset it back to the last commit . Useful for reverting changes you didn't mean to make, especially if you don't know or remember what it was like before. Of course, this can be quite destructive, so be careful.

## Remotes
A remote is a reference to another Git repository somewhere, usually an online Git provider like GitHub, GitLab, or Bitbucket. When you [[#Cloning|cloned]] the Vault, it automatically added the url of our GitHub repository as a remote called "origin", which is convention for the main remote.
>[!note] The url always needs to have ".git" at the end. To get the proper https url of a GitHub project just use `https://github.com/{owner}/{repository name}.git`.

## Push and Pull
Pushing and pulling are the actions of sending and receiving new [[#Commits]] from the [[#Remotes|Remote]]. Technically, it performs [[#Fast-forward]] merges, and when it can't, it creates a [[#Merge Conflicts|Merge Conflict]]. To prevent merge conflicts on the server side, pushing is not allowed if the server has commits you don't.

You can push and pull using the up and down tray arrows, respectfully.

## Branches
I think the best way to explain branches is with a diagram. This one is focused heavily on development, but I think it's still helpful. Each dot is one commit, and each lane/colour is one branch. A branch is actually just a pointer to its last commit. Notice the branches [[#Merging]]!
![git flow diagram|600](https://i.stack.imgur.com/k5Gdu.png)

>[!note] The plugin we're using doesn't have a "graph view", but you can view it on the [GitHub repository.](https://github.com/dykeaura/gaylor-vault/network) It's not a pretty one - GitHub sort of dropped the ball on this feature specifically, because every other Git provider has a nice graph view, and this is the closest we get with GitHub. If you want a nice fancy one, you're gonna have to find some some other app to do that, unfortunately. The GitHub one includes [[Using GitHub#Forks|Forks]] though, so that's nice.

## Merging
Merges are probably the most complicated and intimidating thing about Git. Not without good reason - [[#Branches]] are one of the main parts of Git that level it up above others. Think about how complicated it would be, trying to organize work with a bunch of other people all in one stream? It would be chaos. Well, branches are no good if they always stay separate!
>[!info] The Obsidian Git plugin doesn't seem to have functionality to handle merges. Most will likely be dealt with on GitHub any via [[Using GitHub#Pull Requests|Pull Requests]], but it would still be nice to have *something*. This means that if you need to handle merges locally, you'll need an outside program to help you. Technically, you could just use the command-line and a text editor (Obsidian would be fine for that, I guess, as long as you do it in source mode - the [[#Merge Conflicts|Merge Conflict]] syntax would probably mess with the parsing), but I don't imagine you would find that particularly intuitive. I personally use [GittyUp](https://github.com/Murmele/Gittyup), which is available on Linux, Windows, and Mac. God help you if you need to merge anything on mobile, especially iOS. 🙏

### Types of merges
There are 4 main types of merges (at least, the ones we might use). [[#Fast-forward]], [[#Merge Commits]], [[#Squash]], and [[#Rebase]].

#### Fast-Forward
This is the simplest type of merge. It's what Git uses when you do a [[#Push and Pull|Pull]]. It simply applies all missing commits from the source on top of the destination branch.
![fast-forward diagram|600](https://vanberzon.com/static/290c6b08b5ee0cf9de125379b81ed34f/35c67/fast-forward.png)

#### Merge Commits
This is usually what people mean when they talk about merging with Git. It's where you get the complexity in the pretty graphs from. It's a bit harder to explain. Merge commits have 2 parents instead of just one. Because of that, they have all the changes in both of their parents' histories.
![merge commit diagram](https://docs.github.com/assets/cb-5402/mw-1440/images/help/pull_requests/standard-merge-commit-diagram.webp)

#### Squash
This one takes all relevant commits from the source branch, squashes them into one commit, and puts it on the destination branch. Not good for preserving detailed histories, but occasionally convenient.
![squash merge diagram](https://docs.github.com/assets/cb-5742/mw-1440/images/help/pull_requests/commit-squashing-diagram.webp)

#### Rebase
This one I'm still not sure I understand fully, and that's okay because we probably won't be using it, at least not on the main repo. From what I understand, it takes all the relevant commits from the source branch and re-applies them individually on top of the base branch (not on it - base branch itself is not actually affected at this point), as if they were based off that commit all along. It does that by creating entirely new commits that look exactly like the old ones and rewriting the history. There's even an interactive prompt workflow on the command-line. After rebasing, the base branch can do a simple [[#Fast-Forward]] merge if they want to keep the history linear, or they could do a regular [[#Merge Commits|Merge Commit]] if they want to keep the branch structure and the rebase was just to make the merge simpler.
![rebase diagram|600](https://phoenixnap.com/kb/wp-content/uploads/2023/03/git-rebase-example.png)
>[!warning] If you're the only one who has interacted with the commits you're rebasing (aka the ones that get their history rewritten), then it'll go perfectly fine. But if other people have touched them really at all (looking at them on GitHub doesn't count), then please refrain from doing that.

### Merge Conflicts
A merge conflict arises when you're trying to merge something, but the same thing has been changed in both branches. During a merge, the working tree files are updated to reflect the result of the merge. Among the changes made to the common ancestor’s version, non-overlapping ones (that is, you changed an area of the file while the other side left that area intact, or vice versa) are incorporated in the final result verbatim. When both sides made changes to the same area, however, Git cannot randomly pick one side over the other, and asks you to resolve it by leaving what both sides did to that area.

here's how it looks:
```
Here are lines that are either unchanged from the common
ancestor, or cleanly resolved because only one side changed,
or cleanly resolved because both sides changed the same way.
<<<<<<< yours:sample.txt
Conflict resolution is hard;
let's go shopping.
=======
Git makes conflict resolution easy.
>>>>>>> theirs:sample.txt
And here is another line that is cleanly resolved or unmodified.
```
 Let's pick it apart. 
 1. The first 3 lines are just regular, untouched. That just means that only one or neither side modified it at all.
 2. `<<<<<<< yours:sample.txt`: Beginning of the block that is "yours", aka the base branch, I believe.
 3. 2 lines in the "yours" block
 4. `=======`: Divider between the two sides, aka the end of the "yours" block and start of the "theirs" block.
 5. 1 line in the "theirs" block
 6. `>>>>>>> theirs:sample.txt`: End of the "theirs" block (and the conflict)

#### Solving a merge conflict
To solve a merge conflict, you have to let Git know which side(s) you're taking, then tell it when you're done. You this by going to each instance of a *conflict* (see above) and picking which one (or both/neither?) you want to keep. Then you remove all the fences and version you don't want. When you've gone through all the conflicts, commit, and if it goes through, you're done!
>[!tip] Some third-party Git applications (such as GittyUp, as mentioned earlier) have merge conflict resolution wizards, which offer you all the options, you pick which ones you want, and it does all the behind-the-scenes stuff for you.