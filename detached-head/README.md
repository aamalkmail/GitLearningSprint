# Detached head state

When a user ends up in a "detached head" state, this is a scary situation, but as we know, Git is not scary.

## Setup:

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

1. Run `git status` and `git log --oneline --graph --all` to see what is going on.
2. Restore normalcy in this repository by moving to `master`

Note that this task might seem more confusing if you did not run `setup.sh` in your terminal.

We want to have a branch called `the-beginning` that is made from the first commit with message `A`. 

3. Can you do this by first causing a detached head?
   
```
// Find the hash of the first commit with the message "A"
git log --oneline

// Check out the specific commit using its hash
git checkout a9b1270

// Create a new branch called 'the-beginning' starting from the currently checked out commit
git checkout -b the-beginning

// View the commit history for the new branch
git log –oneline

// Check out the 'master' branch
git checkout master

```
## Useful commands

- `git status`
- `git log --oneline --graph --all`
- `git checkout <ref>` or `git switch --detach <ref>`
