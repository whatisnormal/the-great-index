# Recipes
## "Chunking" changes
Below you will find several techniques to simplify a rebase with another branch.
Imagine we 5 commits but we want to chunk them into a single one.



## Squashing commits
Use _git rebase -i_

Rebase changes your history, so use it with care.

The option _-i_ sets the interactive mode in rebase. It allows us to select what type of actions to do with the last X commits.
It provides several modes: pick (default), squash, between others.
If you remove a commit from the list (pressing 2x in "d" key), and then save, the commit will be lost from your history. 

First run
> git rebase -i head~<number of commits >
  
So if we do 
>git rebase -i head~2
it will pick the last 2 commits 
 
The interactive mode is ordered by first (on top) to last commit.
  
Squash is handled by changing the "pick" mode to "squash" or "s". It will squash with the most recent commit with a previous commit
  
## "Uncommiting" changes back to Stage 
 `git reset --soft HEAD~2 ;
git commit -m "new commit message";
git push -f`

  
