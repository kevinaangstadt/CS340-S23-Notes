# Lecture 7 Notes
# 2/8/23

## Working With Git
The history of a repository forms a tree, or an acyclic graph, where 
there is a linear, unique shortest path from the the root to any 
node (commit) in the tree. Since each node is a 'commit,' then at any
point in time, our working directory is based on some node in the tree.

So when we **commit**, we insert a new node, which become a child of 
the commit the current working directory was based off of. We need a way 
of marking the node or commit that the working directory is based off 
of. This is done with the **HEAD** pointer. 

Now how are we going to be able to move around the tree with random access?
To do this, each commit gets a unique identifier that we call its **hash**. 
Hashes are a fixed length value and represent the data. 

<mark>TODO:</mark> clarify "represent the data"

For convenience, we can make additional labels besides the **HEAD** in 
order to keep track of parts of the version history. We can do this 
with **branches** and **tags**.

## Branches
When we apply a branch label and checkout the branch, future commits 
will move this label with the commits.

## Tags
When we apply a tag to a commit. It will act like a permanent label 
for that commit. 

If we checkout a tag or a commit hash, the head will detach from a 
branch label when we commit, and not labels (apart from the HEAD) 
will move.

---

If we can make new branches, we ultimately need to recombine these 
branches when would want to, for example, accept a new feature or 
apply a bug fix. There are two ways to recombine branches: **merge** 
and **rebase**.

## Merge
A merge combines commits and forms a new commit w/ the combined changes. 
This means the new commit will have *two parents*.

<mark>TODO:</mark> add visual for merge
<mark>TODO:</mark> add code for merge

### Benefits of a Merge:
- Full history of the repository is maintained (can see both parents).
- Merges work well when collaborating because they are often few conflicts to resolve.

### Disadvantages of a Merge:
- Repository can get ugly and confusing with crossing parent lines as different commits are merged.

## Rebase
A rebase will 'copy' commits into another branch. This is like a 
transplant. 

<mark>TODO:</mark> add visual for rebase

The command for the rebase above: `git rebase ` 

More generally: `git rebase <branch_name>`

### Benefits of a Rebase:
- Can keep the repository cleaner (changes are cleanly inserted without ties to parents).
- Rebases work well when working with personal local edits because you can "clean up" personal mess before sharing commits

### Disadvantages of a Rebase:
- Repository history/topology isn't maintained.

***Warning!*** **Do not** rebase commits that exist outside your local repository that people may have basen work on.

---

## Commit Messages
Everything we have mentioned so far references commits extensively, so 
what is a needed for a good commit message?

Every time we commit, we should provide a message about the commit. When 
writing messages, there are a few standard idioms that you should follow.
Generally, a commit message should describe the problem being fixed or 
the feature being added in the commit, as well as why the change is 
being made. The message should be able to stand on its own (no links 
to other places) and shouldn't assume access to outside resources.

Structure wise, one can this of a commit message being similar to a 
letter. The first line of a commit message should be the subject of 
the commit. Subsequent lines are the message body and should include 
the what, why, etc., as well as list any known limitation to do with 
the commit. Text for commits should be wrapped at 72-80 characters.

The Golden Rule for Commits: the commit message must contain all info 
required to fully understand and review the patch/changes for correctness.

### The Do's and Don'ts of Commits:

When commiting...

### don't...
- mix whitespace/formatting changes with functional code changes
- mix unrelated functional changes
- submit all code as a single commit

### do...
- try to keep commits small and modular

Small commits makes it easier to review, revert, "blame", and troubleshoot!
