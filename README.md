# GitHub Tutorial

_By : Johnson Wu_

---
## Git vs. GitHub
* #### Git
    * version control
    * keep "snapshots" of codes
    * does not require github
* #### Github
    * store code in the cloud or online
    * visually track changes
    * requires git  

---
## Initial Setup
1. _Create Github Account_
    1. Go to [Github](https://github.com)
    2. Click on _"Sign Up"_ on top right
    3. Complete all steps in creating your account
    4. After you've successfully created your Github account, explore Github and get familiar with it
2. Create a SSH key between your Github and c9
    1. In Github, click on your profile icon on the top right
    2. Click on _"Settings"_
    3. On the leftside bar click on _"SSH and GPG keys"_
    4. Click on _"New SSH key"_
    5. For the title put _"cloud9"_
    6. Open a new tab and go to your [c9](https://c9.io/) account
    7. After you've logged on to your c9 account click on the gear icon on the top right
    8. Click on _"SSH Keys"_ then copy the **second SSH key** to your Github and press _"Add SSH key"_
    9. Finally go back to your cloud9 and open your "github-learning" IDE then type in `ssh -T git@github.com`. You should see `Hi <your username>! You've successfully authenticated, but GitHub does not provide shell access._`. This means that you've successfully created an SSH key between your Github and c9. If not, you must have done something wrong or there might be an error so please ask for **help**.

---
## Repository Setup
Now that you've created a github account and SSH key let's create your first repository!
1. In your "github-learning" IDE in your c9, make a new directory called `first-repo` by typing `mkdir first-repo`
2. Go into your `first-repo` directory using `cd first-repo`
3. Type in `git init`. This initilizes git in the directory making it now a local repository for version control. You only need to do this once to one directory you want to initialize git in.
4. Create `README.md` file by typing `touch README.md`
5. Open `README.md` file using `c9 README.md` and type in anything you like
6. Save the file then add the file to the staging area using `git add filename` (for filename put the name(s) of the file(s) you want to add to the stage)
7. Commit your file using `git commit -m "message"`
8. Open a new tab and go to your Github account 
9. Once you've logged onto your Github account click on the "+" icon on the top right then click on "New repository". _**If it ask to verify your email, verify it**_.
10. For the repository name type in "first-repo" because _**the repository name on your github must always match your repository name on c9**_ then click on "Create repository"
11. Now you should be somewhere that says "Quick setup - if you've done this kind of thing before" _**make sure you have SSH selected**_
12. Copy and paste the line of code that says `git add remote origin URL` to your c9. This creates a connection between your local repository (in c9) and your remote repository (in github). Then copy and paste the line of code that says `git push -u origin master` to your c9. This creates a default pathway to a remote repository on your github where you'll push your committed file(s) from your local repository to.
13. To check if you've successfully created a remote use `git remote -v`
14. To delete a remote use `git remote rm origin`

---
## Workflow & Commands
Now that you've created your Github account and created your first repository, here are some tips when working with git and github.
1. Always use `git status` when working with git. `git status` shows you the status of your work. For example, it will show you which file(s) you've edited since your last commit (it'll appear in red) and it will show you the file(s) you've added to the stage ready for commit (it'll appear in green). Also if you want to undo edits or adds it will tell you how to do so in `git status`
2. It's important that every time you make edits to your work, you use `git add filename` , `git commit -m "message"`, and `git push`. `git add filename` adds your file(s) to the stage ready to be commited. In a photo-taking scenario `git add filename` is like adding people to the stage ready to take a photo. `git commit -m "message"` takes a "snapshot" of the file(s) you've added to the stage. For the message you put what you've modified or changed in the file(s) before you've added them to the stage and they should be in present tense. `git push` pushes your committed file(s) from your local repository in c9 to your remote repository in github.
---
## Rolling Back Changes
If you've accidentally edited a file, add a file, commit a file, or push your work here's how you undo them:
* To undo an edit use `git checkout -- filename`. This will change your work back to your previous commit. You can use this in many cases. For example you may want to undo an edit when you accidentally edited a wrong file.
* To undo an add use `git reset HEAD filename`. This will remove the file(s) you've added to the stage. This is a helpful git command because if you've accidentally added multiples of files to the stage when you only want to add just one of them to the stage then you can undo the adds using this command.
* To undo a commit use `git reset --soft HEAD~1`. This will undo the snapshot of your file(s) you've added to the stage. You can use this command when you realized that you forgot to add a file to the stage to be committed after you've committed.
* To undo a commit and an add use `git reset HEAD~1` This will undo the snapshot of the file(s) you've added to the stage and remove the file(s) from the stage. You may want to use this command when you realized that you made a mistake in a file after you added and committed that file.
* To undo an edit, an add, and a commit use `git reset --hard HEAD~1` This will bring you back to your previous commit. You may want to do this when you've realized that you've made unecessary edits to a file after you edited, added, and committed that file.
* To undo a push use `git revert`. This will bring you back to your previous commit. You can use this when you realized that your previous commit was fine after you `git push`.
























