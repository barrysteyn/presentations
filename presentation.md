# Git
## How It Works, Why It's Better

By [Barry Steyn](basteyn@microsoft.com)

~

# Understanding Git
### This Lecture Is Not About How To Use Git

You have the internet for that (see resources at last slide)

~

# Understanding Git
### What This Lecture Is About

  * How to think of Git
  * Why using it is better than SD
  * How we can be more productive with a simple workflow

~~

# How To Think Of Git
### Git Is Really Just A Graph

  * Nodes are commits, represented as SHA1 hashes
  * Edges are deltas representing changes betweenn nodes

~

# HEAD
### HEAD is commit that designates the tip of the current branch

  * Giving a branch a name implies associating a name with HEAD

~

# Git Branching
## Considered Git's Killer Feature

  * A branch is really just an index to a commit: The HEAD which points to the tip
  * The path from the tip through all the parents is considered the branch path
  * **It is incredibly low overhead to create a branch**: Just as much overhead as creating another commit

Every Git repo has a branch that is by default named **master**
~

# Git Branch Merging
### Many merge algorithms, most common one is normal three way merge

  1. Common ancestor
  2. The HEAD of the branch that will be merged
  3. The HEAD of the branch that will be merged into

~

# Git Rebasing
### You can move any node in the graph by *replaying* them
This is essentially what a rebase is - it is normally used to neaten the Git Graph

~

# Git Graph Navigation
### You can also move to any node in the graph with ease

This means you can easily get to the exact state of that node in the graph

~

# Git Graph Recap
## Git is a graph

   * The graph can be merged
   * The graph can be rebased (re-ordered)
   * You can move to any node of the graph with ease

~~

# Git Is Distributed
### You have your own local graph

**Terminology**: The *remote* is a machine that hosts the graph that we consider to be the central source of truth

~

## Your mission is to make your local graph agree with the remote graph

   * You can clone the remote graph (only done at the beginning)
   * You can push commits to the remote graph
   * You can pull commits from the remote graph

~

# Working In A Team

   * You commit to your local graph in a your own branch
   * You push your local branch to the remote
   * You then need to merge your local branch into the master branch

</br>
Git allows us to the do the above with relative ease, even in a large team <br/>
**CAVEAT**: You need to understand Git and know what it is doing

~

# Rebasing
## Rebasing allows you make the Git history cleaner

   * It makes it easier to follow history
   * Yet... it can also be vital to workflow


~~

# Git Flow
## You need a workflow for a team to work effectively

   * Most newbies go online and find something called Git Flow
   * It is the most complex workflow out - in my experience, everyone has to be a Git Ninja
   * It also adds too much overhead

~

# A Simple Git Workflow

**In A Nutshell**

   * Devs create their own branch and push to the remote
   * When time comes to merge (commit to production), they rebase their work onto lastest master locally
   * They then do a fast-forward merge to remote

~~

# The End

   * Git Book: https://git-scm.com/book/en/v2
   * Git Interactive Demo: http://pcottle.github.io/learnGitBranching

Barry Steyn