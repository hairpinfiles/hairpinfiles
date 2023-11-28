---
title: GitHub
description: information about navigating and using GitHub
author: dykeaura
---
GitHub is a place to keep [[./git|Git]] repositories - it's usually used for code, really can be useful with any project made up of mainly text files. Good news for us, that describes our Vault perfectly!

You'll need an account, of course. I assume you can find the button that says "Sign Up"? Click it and follow along. I don't mean to be blunt, but if you can't figure out how to create an account, then I'm not sure how to help you. 🤷

Anyway - there's probably something you're looking for here. If you're new and don't know what you're doing, try [[#Issues]].

## Issues

Look at the issues page [here](https://github.com/hairpinfiles/hairpinfiles/issues).
Issues are sort of like a big bin of tasks for the whole vault. They represent **things to be done.** Take for example, [#2](https://github.com/hairpinfiles/hairpinfiles/issues/2) (the one I'm working on right now!)

- It's called "Write a contribution guide"
- It's assigned to _dykeaura_ (me)
- it has the [[#Labels]] "addition" and "meta"

With a keen eye, you may have also noticed how I linked to it, with "#2". The 2 here refers to the issue _id_, and you can also find it next to the title, a little greyed out. In Obsidian, you have to manually link to it (actually, I have a regex set up to do it automatically, but you don't want to hear about that), but on GitHub, it does it automatically. These ids are not only for the issues, but they are shared with [[#Pull Requests]] and [[#Discussions]]. Don't worry about those yet.

When we're done with an issue (which usually means we finished the task, or decided we wouldn't do it at all), we can close it. This is basically just like checking it off our list - mostly a cosmetic thing and doesn't really have an effect other than let us filter it and help us than see what's going on at a glance, so we can move on and work on something else. It turns the icon of the issue (a circle with a dot in the middle) from _green_ to _purple_ (if it gets closed as "not planned", it turns grey).

### Labels

Labels are sort of like categories for the issues. If there's a lot of them (large projects often have thousands open at a time!), it can be difficult to parse through them all just by title and description alone. So labels mainly provide a filtering utility, as well as give us some other information about the issue before we click on it, sort of like seeing tags on an article. All labels have descriptions that should appear when you hover over them, or you could view all of them and their descriptions [here](https://github.com/hairpinfiles/hairpinfiles/labels).

## Pull Requests

A pull request is a request to [[./git#Merging|Merge]] one [[./git#Branches|Branch]] into another. They're pretty simple, actually, not much different from [[#Issues]]. They share the [[#Labels]] functionality, and can also be assigned to people, projects, and milestones, just like issues. The only difference (other than the whole purpose) is that you can assign _reviewers_. They get a notification and let you know what they think of your pull request. (I think they vote?). Once your pull request is merged, the icon turns purple like an issue. If it gets rejected (probably will happen pretty rarely in the Vault unless hetlors use it to harass us or something), the icon turns red instead. It's common practice for the branch that the pull request was merged from to be deleted afterwards, and GitHub can do this automatically.

> [!tip] 
> If you're not ready to actually merge the pull request yet (like if you're not quite done working on it), then you can mark it as a draft, and GitHub will prevent it from being merged until it's removed.

## Forks

A fork is essentially a copy of a repository on a different account or organization. It's very useful to be able to work on something independently without affecting the original project until you want it to. There are two main reasons to fork something, and the only real difference is whether you want to [[./git#Merging|Merge]] back into the original or not. You might want to create your own version of something separate from the original, or you might want to contribute to the original. Your case with the Vault is probably the latter.

### Create a Fork

On the [main repository page](https://github.com/hairpinfiles/hairpinfiles), find and click the button that says "fork" as shown below. It should be somewhere in the top right.

![](https://i.imgur.com/kONSuAZ.png)

You can then optionally change the name and/or description of the project - I recommend not changing the name if you're wanting to contribute, it helps make it clear that's what you're trying to do. I would also keep the "copy the master branch only" checkbox checked, any others are typically not relevant to you.

It's good practice to create a new [[./git#Branches|Branch]] on your fork with a descriptive name for your contribution. If there's already an [[#Issues|Issue]] about your contribution, you can create it from there. It will be linked and shown to anyone viewing the issue. Supposedly it also gets automatically closed when the associated [[#Pull Requests|Pull Request]] gets merged, but in my experience it doesn't pick up the pull request properly for some reason, so I manually link it with "closes #{ID}" at the bottom. (which also helps make it clear to other people)

When you're done working on your contribution, find the "contribute" dropdown button like shown below: (make sure you're on the right branch)

![](https://i.imgur.com/b6LQcCF.png)

Click on it and then the "open pull request" button that pops up. See [[#Pull Requests]] for tips on working with those.
