# Setting up a Dev Container For Go 
* Primary author: [Ana Restrepo](https://github.com/analrest)

## Prerequisites
### Make sure you have:
* A github account
* Git installed
* VS Code installed
* Docker installed

## GO Instructions
### First you are going to make a local directory and initialize git
* You can do this by going to your computer's terminal and typing: mkdir comp423-go 
* Next you will type: git init 

### Next step is to create a README file 
* You can do this by typing: echo "# COMP423 Go" > README.md
* then type: git add README.md
* then: git commit -m "Initial README commit"

### Now you will create a remote repository on GitHub
* log into your github and go to Create a New Repository page and fill in the name "comp423-go", the description "comp 423 learning go", and visibility "public"
* DO NOT initialize the repository with a README, .gitignore, or license
* Now click Create Repository

### Next you will link your local repository to GitHub
* Type "git remote add origin https://github.com/<your-username>/comp423-course-notes.git" to add the repository as a remote
* Next check that your default branch name is main using "git branch"
* If it is not main, then change it to main by typing "git branch -M main"
* Finally push you local commits to your repo by typing "git push --set-upstream origin main"

### We will now set up the development enviorment
* 
