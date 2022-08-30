# Base GIT Configs to setup
## Set name and email
>git config --global user.name "Mohammad-Ali A'râbi"

>git config --global user.email "my-name-at-work@employer.com"

remove the option --global to set repo specific config
>git config user.email "my-personal-id@gmail.com"

## Default branch name
> git config --global init.defaultBranch <name>

## Rebase as default pull method

I always hate it when I pull and a merge commit is created. Especially, when I’m developing on master and I cannot push anymore afterward (because the local branch is not ahead of the remote one).
  
> git config --global pull.rebase true

## Auto stash
Having a clean master is not the only benefit of using rebase as the default pull action. By setting the following config, one does not need to stash their WIP before pulling, because will do it automatically:
  
> git config --global rebase.autoStash true

## force with lease
As someone who rebases, I need to push to the remote branch with --force-with-lease a lot. And it’s boring to write the whole thing every time:
  
> git config --global alias.enforce "push --force-with-lease"
> git enforce

## Default name upon push
Imagine you have created a new branch and want to push it to the remote repo for the first time. Git will complain and say that you should set the upstream:
  
> git push -u origin the-same-name-as-my-current-branch

This whole workflow is super annoying. That’s why there is a config to automate it:


> git config --global push․default current

  
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

  
