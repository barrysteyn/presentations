# Git Basics
### How To Use Git Effictively In A Team

Created by [Barry Steyn](basteyn@microsoft.com)

~~

# Git
 1. Distributed
 2. Light weight branches

~

#How To Think Of Git
## Think of it as a graph:

 * There are graph nodes (git commit)
 * You can move to any node (git checkout)
 * You can change the history of the graph (git rebase)

~

#Git: Exchange States
##Your Goal: To get your *private* state exchanged for the shared state

Git can do this elegantly, but it is also very easy to make a mess.

~~

# Three Simple Rules
 1. Work in feature branches
 2. Rebase and push often
 3. Fast forward merge into shared branches

<u>Tip</u>: Use source tree often to look at a tree view of your git repo

~~

# Feature Branches
##Branching is core to git:

 1. Light weight
 2. Quick to create
 3. Quick to delete

The master branch is special: It is considered the shared source of truth

~

# Feature Branches
##A *short lived* branch created to accomplish a task
###Think of a feature branch as your private space - GO WILD!

As soon as these branches have been rebased/merged, they should be deleted

~

# Feature Branches
##They are not meant to be shared

<u>Clarification</u>: When you are git guru, go ahead and use other feature branches

In the mean time: Never *EVER* merge a feature branch. This is a recipe for making a mess

~

# Feature Branches Vs Shared Branch
## Shared branches contain state that is shared (and agreed upon) by everyone

We have just one shared branch: <u>master</u>

~~

# Rebase And Push Often
##First thing after creating a branch locally: <u>push it to the remote</u>

Don't forget to set up your tracking (done automatically on visual source safe)

~

# Rebase And Push Often
## Rebase the shared branch (master branch) onto the feature branch

~

# Aside: Rebase Vs Merge
<div style="text-align: left;">
###<u>Merge</u>: takes all changes in one branch, and brings them into another branch in one commit
###<u>Rebase</u>: move the point where the current branch starts to a new starting point
</div>
But a picture is worth a thousand words...

~

# Rebasing
## Rebase is done for two reasons:

 1. To neaten the history
 2. To perform fast forward commits

<br>
There is a subtle difference between the two items above: A fast-forward commit guarantees no conflicts, thus rebasing implies conflicts have already been sorted.

~~

#Fast-Forward Merge
## Once work is ready to be "shared", it is merged into the shared branch
This merge is a fast-forward merge

~

#Fast-Forward Merge
##It is a merge, and so pull-requests are valid

Therefore, code reviews can be done

~

#Aside: Pull Requests
##A better description is a merge request
The reason why it is called pull request is due to GitHub where whole projects are merged

~

#Aside: Pull Requests
##A pull request is a step performed before merging
Code can be checked (reviewed), and thumbs must be given. Automated tests should be run at this stage.

~~

#The End
By Barry Steyn