So you want to lend your hand at making the Vault just a little bit better. Great! ...Where do you start? It depends on how you want to help. If you just want give us suggestions of pages to add or let us know about typos you notice, head over to [[Using GitHub#Issues|Issues]]. If you want to do something yourself, read on. 
>[!note] This tutorial (and a lot of the others) are pretty technical - not everyone will be able to get comfortable with the whole process (or any of it). If there's anything you need help with, or even if you want to forgo all the technical stuff and just submit stuff to me directly - just let me know. Find me on twitter (@dykeaura), or discord(@oreothepony), put it in your issue, or even send me an email (dykeaura@gmail.com). I want to lower the barrier of entry as much as possible, so let me know what you need and I'll adapt to it as much as I possibly can.
## 1. Decide what you want to work on
Take a look at the [issues tab](https://github.com/gaylor-wiki/gaylor-vault/issues) - if you have something in mind already, try searching for it to check if someone else has already thought of it. If there aren't any, create one yourself. If you don't know what you want, scroll through them a bit, see if anything catches your eye. If you want to work on an issue (including your own), assign yourself. 
>[!tip] Other than on the side bar editor thing if you have more than just read permissions, you can assign yourself by posting a comment with ".take" somewhere in it. Try it in the issue body, even. **This is specific to the Vault**, implemented via GitHub Actions.

## 2. Make sure you have a fork
If you've already created one before, you can just make sure it's synced and then create a new branch.
![[Using GitHub#Create a Fork]]

## 3. Make sure you're set up in Obsidian
Use the url of your fork instead of the main repo to clone, or if you did it already, you can change it with the following:
1. Run the command "Obsidian Git: Edit Remotes", and pick "origin".
2. Enter your new url.

![[Using Obsidian#Quick Start Guide]]

## 4. Make sure you're in sync with `master`
If you just cloned it, you won't have to worry about this, but otherwise, make sure you pull before you make any changes to anything. Otherwise you might end up with a [[Using Git#Merge Conflicts|Merge Conflict]], and nobody wants that.

## 5. Make your changes
Here's where you really take the reigns. Keep an eye on [[STYLE_GUIDELINES]], and have fun!

## 6. Submit a Pull Request
Two ways:
1. Go to your fork, make sure you're on the right branch, click the "contribute" button, then "open pull request".
2. Go to the pull requests tab on the main repo, click "new pull request", click "compare across forks", then change the repo and branch on the right to the ones from your fork.
Keep the title short, and put more details in the description. Put "Closes #{`ID`}" at the bottom, where `ID` is the id of the issue that you created or claimed.

If you want to get someone's opinion before you merge, you can assign them as a reviewer. Or, if you don't have write permissions and they've agreed to merge it for you. (keyword: agreed - don't pick a random person you haven't asked, it's rude and just adds confusion)

Otherwise - if you have write permissions, you can just merge it yourself. If you don't, please be patient and wait for someone else to do it, it should be done within a couple days or so.

## 7. Celebrate when it gets merged
In my opinion, there's no better feeling than contributing to a community project with your friends, especially a community as special as gaylor. 🥳🎉