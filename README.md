# Lab-05
## Exercise 1 - Revert

#### Cloning a repo
- Go to a playground folder using explorer (c:\temp, for example)
- Right click inside the folder and select 'GitExt Clone...'
- Paste the URL https://github.com/noama-demo/Lab05-ex1.git and choose clone

#### Inspecting the error
- Checkout master branch
- Inspect print-lines/Program.cs using the Split View -> File Tree (line 22)
- Identify the error origin:
    - Select both commits:
        - c189106 (comment: Add Line 5)
        - a29e5e6 (comment: Mistake)
    - In the Split View -> Diff, verify that a29e5e6 introduce the error

#### Fixing the error using revert
- Ensure that master branch is checked out (we will fix it)
- Right click the a29e5e6 commit and choose 'Revert this commit'
- From the Button Bar, open the commit window, verify the stages files and content and press 'Commit'

#### Validate the error is fixed
- Validate the print-lines/Program.cs in the master branch is fixed 

## Exercise 2 - Cherry-pick
Continue using the same repo as before

#### Inspecting the Issue
- Checkout master branch
- Inspect an issue with print-lines/Program.cs using the Split View -> File Tree (line 15, missing ;)
- Identify an already made fix in a hotfix branch:
    - Select both commits:
        - 15f64c2 (comment: Add Line 3)
        - 5f764ac (comment: Fix line 3) 
    - In the Split View -> Diff, verify that 5f764ac4 fixed the missing ; error

#### Fixing the issue using cherry-pick
- Ensure that master branch is checked out (we will fix it)
- Right click the 5f764ac4 commit and choose 'Cherry-pick this commit'
- Leave all defaults and Click 'Cherry-Pick'

#### Validate the error is fixed
- Validate the print-lines/Program.cs in the master branch is fixed 

## Exercise 3 - Reset
Continue using the same repo as before

#### Inspecting state
- Checkout poc branch
- Inspect the print-lines/Program.cs using the Split View -> File Tree

#### Reset the poc branch to an old commit
- Checkout poc branch
- Right Click commit 02d848e (comment: Add Line 2) and choose 'Reset current branch to here'
- Press OK

#### Validate the reset
- Checkout poc branch - view its commit SHA
- Notice that your working directory contains the file from 5f764ac, so you won't lose data.
