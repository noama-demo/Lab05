# Lab-05
## Exercise 1 - Revert
### Overview
In this exercise, we will use revert to undo a commit in history  
This is like rollback - adding a new commit to fix the old one

#### <u>Cloning a repo</u>
- Go to a playground folder using explorer (c:\temp, for example)
- Right click inside the folder and select 'GitExt Clone...'
- Paste the URL C:\GitServer\labs\Lab05-ex1 and choose clone

#### <u>Inspecting the error</u>
- On the left pane, right click <i>Remotes -> Origin -> master</i> branch and select <i>Fetch & Checkout</i>. This will create our local <i>master</i> branch. Press <i>Checkout</i> if required.
- Inspect <i>print-lines/Program.cs</i> using the <i>Split View -> File Tree</i> (line 22) and identify the error (ERROR)
- Inspect commit <i>a29e5e6</i> (comment: Mistake) and check <i>print-lines/Program.cs</i> using the <i>Split View -> File Tree</i>
- Verify that a29e5e6 introduce the error using the <i>Split View -> Diff</i>

#### <u>Fixing the error using revert</u>
- Ensure that master branch is checked out (we will fix it)
- Right click the <i>a29e5e6</i> commit and choose <i>Revert this commit</i>
- When requested, click <i>Revert this commit</i>
- From the <i>Button Bar</i>, open the commit window, verify the staged files and content and press <i>Commit</i>

#### <u>Validate the error is fixed</u>
- Validate the print-lines/Program.cs in the master branch is fixed 
- Validate the new commit message. It has all the details of the revert

## Exercise 2 - Cherry-pick
### Overview
In this exercise, we will use cherry-pick to undo a commit in history  
This is like rollback - adding a new commit to fix the old one  
Continue using the same repo as before

#### <u>Inspecting the Issue</u>
- On the left pane, right click <i>Remotes -> Origin -> master</i> branch and select <i>Fetch & Merge (Pull)</i>. This will create our local <i>master</i> branch. Press <i>Merge</i> if required.
- Inspect an issue with <i>print-lines/Program.cs</i> using the <i>Split View -> File Tree</i> (line 15, missing ;)
- Identify an already made fix in a hotfix branch:
    - Select commit <i>5f764ac</i> (comment: Fix line 3) 
    - In the Split View -> Diff, verify that 5f764ac4 fixed the missing ; error

#### <u>Fixing the issue using cherry-pick</u>
- Ensure that master branch is checked out (we will fix it)
- Right click the 5f764ac4 commit and choose 'Cherry-pick this commit'
- Leave all defaults and Click 'Cherry-Pick'

#### <u>Validate the error is fixed</u>
- Validate the print-lines/Program.cs in the master branch is fixed 
- Validate the new commit message. It has all the details of the cherry-pick

## Exercise 3 - Reset
### Overview
In this exercise, we will use reset to undo our last two commits. We can do it, since we haven't pushed the commits yet.    
This action will nodify the history, so we will not perform it on a remote branch  
Continue using the same repo as before

#### <u>Checkout our master branch</u>
- On the left pane, right click <i>Remotes -> Origin -> master</i> branch and select <i>Fetch & Merge (Pull)</i>. This will create our local <i>master</i> branch. Press <i>Merge</i> if required.
- Inspect the <i>print-lines/Program.cs</i> using the Split View -> File Tree and notice both our fixes.

#### <u>Reset the master branch to the old commit</u>
- Right Click commit </i>ee06ad7<i> (comment: Merge branch 'bugfix/cherry-pick' into 'master') and choose <i>Reset current branch to here</i>
- Press OK

#### <u>Validate the reset</u>
- Inspect the <i>print-lines/Program.cs</i> using the Split View -> File Tree and notice both our fixes are gone.
- Notice that the working directory contains the file from our last reset commit, so we won't lose data.
