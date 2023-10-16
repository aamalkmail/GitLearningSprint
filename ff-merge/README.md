# Git Kata: Fast-forward Merge

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You again live in your own branch, this time we will be doing a bit of juggling with branches, to show how lightweight branches are in git.

1. Create a (feature)branch called `feature/uppercase` (yes, `feature/uppercase` is a perfectly legal branch name, and a common convention).
2. Switch to this branch        
```
// Create a new branch called 'feature/uppercase' and switch to it
$ git checkout -b feature/uppercase
```
3. What is the output of `git status`?             
  **It shows that I’m on the 'feature/uppercase' branch and that there are no changes to be committed**        
4. Edit the greeting.txt to contain an uppercase greeting
5. Add `greeting.txt` files to staging area and commit
  ```
    $ git add greeting.txt
    $ git commit -m "Changed greeting to uppercase"
  ```
6. What is the output of `git branch`?             
  **It shows a list of branches. the 'feature/uppercase' branch and the 'master' branch**     
7. What is the output of `git log --oneline --graph --all`          
  **It shows the commit history in a graph format, displaying both branches and their respective commits. I  see the commit that I have made in the 'feature/uppercase' branch**        

   *Remember: You want to update the master branch so it also has all the changes currently on the feature branch. The command 'git merge [branch name]' takes one branch as argument from which it takes changes. The branch pointed to by HEAD (currently checked out branch) is then updated to also include these changes.*

8. Switch to the `master` branch
```
  $ git checkout master
```
9. Use `cat` to see the contents of the greetings
```
  $ cat greeting.txt //hello
```
10. Diff the branches
```
  $ git diff master feature/uppercase
```
11. Merge the branches
```
  $ git merge feature/uppercase
```
12. Use `cat` to see the contents of the greetings      
 ```
  $ cat greeting.txt //HELLO
```         
13. Delete the uppercase branch
```
  $ git branch -d feature/uppercase
```

## Useful commands

- `git branch`
- `git branch <branch-name>`
- `git branch -d <branch-name>`
- `git switch`
- `git branch -v`
- `git add`
- `git commit`
- `git commit -m`
- `git merge <branch>`
- `git diff <branchA> <branchB>`
- `git log --oneline --graph --all`
