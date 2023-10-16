# Git Kata: Basic Staging

This kata will examine the staging area of git.

In git we are working with three different areas:

* The working directory where you are making your changes
* The staging area where all changes you have added through `git add` will stay
* The repository where every commit ends up, making your history. To put your staged changes in here you issue the `git commit` command.

A file can have changes both in the working directory and staging area at the same time.
These changes do not have to be the same.

We will also work with `git restore` to restore the staged changes of a file, and `git checkout` to return a file to a previous state.

## Setup

1. Run `source setup.sh` (or `.\setup.ps1` in PowerShell)

## The task

You live in your own repository. There is a file called `file.txt`.

1. What's the content of `file.txt`?             
  **It contains the number "1".**       
2. Overwrite the content in `file.txt`: `echo 2 > file.txt` to change the state of your file in the working directory (or `sc file.txt '2'` in PowerShell)
3. What does `git diff` tell you?              
  **It show  the changes made to the file since the last commit. It indicate that "1" was replaced with "2."**    
4. What does `git diff --staged` tell you? why is this blank?         
  **This command was blanked because I haven't staged the changes yet (I haven’t add the changes yet)**        
5. Run `git add file.txt` to stage your changes from the working directory.
6. What does `git diff` tell you?              
  **It still show the same changes as before**            
7. What does `git diff --staged` tell you?             
  **It shows the changes I've staged, which is the replacement of "1" with "2."**             
8. Overwrite the content in `file.txt`: `echo 3 > file.txt` to change the state of your file in the working directory (or `sc file.txt '3'` in PowerShell).
9. What does `git diff` tell you?            
  **It shows the changes I made from "2" to "3".**                
10. What does `git diff --staged` tell you?               
  **It shows the changes I've staged, which is the replacement of "1" with "2." (which was staged previously)**       
11. Explain what is happening            
  **In this step, I have changed the content of file.txt from "2" to "3" in my working directory. However, I haven't staged these changes, which is why git diff --staged still shows the staged change from "1" to "2."**          
12. Run `git status` and observe that `file.txt` are present twice in the output.       
  **I see file.txt listed twice: one with changes not staged for commit and one with changes to be committed**        
13. Run `git restore --staged file.txt` to unstage the change
14. What does `git status` tell you now?      
  **‘git status’ shows file.txt as "Changes not staged for commit."**        
15. Stage the change and make a commit
16. What does the log look like?            
  **The commit log show two commits: one for the change from "1" to "2" and another for the change from "2" to "3."**       
17. Overwrite the content in `file.txt`: `echo 4 > file.txt` (or `sc file.txt '4'` in PowerShell)
18. What is the content of `file.txt`?         
  **It contains the number "4."**     
19. What does `git status` tell us?               
  **It shows file.txt as "Changes not staged for commit."**      
20. Run `git restore file.txt`
21. What is the content of `file.txt`?            
  **It contains "3" again, reverting the changes made in step 17**     
22. What does `git status` tell us?            
  **It confirms that there are no uncommitted changes in the working directory, making the working tree clean**                 

## Useful commands

- `git add`
- `git commit`
- `git commit -m "My lazy short commit message"`
- `git log`
- `git log -n 5`
- `git log --oneline`
- `git log --oneline --graph`
- `git restore --staged`

## Aliases

You can set up aliases as such:
`git config --global alias.lol 'log --oneline --graph --all'`
This might be useful to you.
