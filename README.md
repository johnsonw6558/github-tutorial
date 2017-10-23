# GitHub Tutorial

_By : Johnson Wu_

---
## Git vs. GitHub
* #### Git
    * version control
    * keeep "snapshots" of codes
    * does not require github
* #### Github
    * store code in the cloud or online
    * better and more efficient way to track changes because it allows the coder to visually track changes
    * requires git  

---
## Initial Setup
1. Create Github Account
    1. Go to https://github.com/
    2. Click on "Sign Up" on top right
    3. Complete all steps in creating your account
    4. After you've successfully created your github account. Explore github and get familiarize with it.
2. Create an SSH key between your github and c9
    1. In github click on your profile icon on the top right.
    2. Click on "Settings"
    3. On the leftside bar click on "SSH and GPG keys"
    4. Click on "New SSH key"
    5. For the title put "cloud9"
    6. Open a new tab and go to your [c9](https://c9.io/) account
    7. After you've logged on to your c9 account click on the gear icon on the top right
    8. Click on "SSH Keys" then copy the _**second SSH key**_ to your github and press "Add SSH key"
    9. Finally go back to your cloud9 and open your "github-learning" IDE then type in `ssh -T git@github.com`. You should see `Hi <your username>! You've successfully authenticated, but GitHub does not provide shell access._`. If not you must have done something wrong or there might be an error so please ask for help.

---
## Repository Setup
Now that you've created a github account and SSH key let's create your first repository!
1. In c9 `cd` into your workspace 
2. Make a new directory called `first-repo`
3. `cd` into `first-repo`
4. Initialize git in `first-repo` by typing in `git init`
5. Create `README.md` file
6. Open `README.md` file and type in anything you like
7. Save the file then add the file to the staging area using `git add <filename>`
8. Commit your file using `git commit -m "<insert message>"`
9. Open a new tab and go to your github account 
10. Once you've logged on to your github account click on the plus icon on the top right then click on "New repository". _**If it ask to verify your email verify it**_.
11. For the repository name type in "first-repo" (_**remember the repository name on your github must always match your repository name on c9**_) then click on "Create repository"
12. Now you should be somewhere that says "Quick setup - if you've this kind of thing before" _**make sure you have SSH selected**_.
13. Copy and paste the line of code that says `git add remote origin URL` to your c9 first then copy and paste the line of code that says `git push -u origin master` to your c9
14. To check your remote in your c9 use `git remote -v`
15. To delete the remote use `git remote rm origin`

---
## Workflow & Commands
Now that you've created your github account and created your first repository, here are some tips when working with github.
1. always use `git status` to check the status of your work.
2. everytime you've made edits to your work add it to the staging area using `git add filname` then commit it using `git commit -m "message"` then `git push` it to your remote in github.

---
## Rolling Back Changes
If you've accidentally edited your work, add a file, commit a file, or push your work here's you you undo them:
* To undo an edit use `git checkout -- filename`. This will change your work back to your previous commit
* To undo an add use `git reset HEAD filename`
* To undo a commit use `git reset --soft HEAD~1`
* To undo a commit use `git revert`
* To undo a commit and an add use `git reset HEAD~1`
* To undo an edit, an add, and a commit use `git reset --hard HEAD~1`