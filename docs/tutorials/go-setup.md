# Setting up a Dev Container For Go
### *In this page we will learn how to set up a dev container and print in the terminal Hello COMP423 using the language Go!*

Primary author: [Ana Restrepo](https://github.com/analrest)

## Prerequisites
### Make sure you have:
* A github account
* Git installed
* VS Code installed
* Docker installed

## GO Instructions
### 1. First you are going to make a local directory and initialize git
* You can do this by going to your computer's terminal and typing ```mkdir comp423-go ```
* Next you will type ```cd comp423-go```
* Finally you will type ```git init ```

### 2. Next step is to create a README file 
* You can do this by typing ```echo "# COMP423 Go" > README.md```
* Then type ```git add README.md```
* Then ```git commit -m "Initial README commit"```

### 3. Now you will create a remote repository on GitHub
* Log into your github and go to Create a New Repository page and fill in the name "comp423-go", the description "comp 423 learning go", and visibility "public"
* **DO NOT** initialize the repository with a README, .gitignore, or license
* Now click Create Repository

### 4. Next you will link your local repository to GitHub
* Type ```git remote add origin https://github.com/<your-username>/comp423-go.git``` to add the repository as a remote
* Next check that your default branch name is main using ```git branch```
* If it is not main, then change it to main by typing ```git branch -M main```
* Finally push you local commits to your repo by typing ```git push --set-upstream origin main```

### **Explanation of a dev container**
A dev container is like a shipping container in that it has predetermined measurements. A dev container is a preconfigured environment that is defined by a set of files which helps provide consistent setups when working with other developers. This solves the "it works on my computer" problem that often happens when working with other developers because now everyone will have identical environments.

### 5. We will now set up the development environment
* Open VS Code and then File > Open Folder and find "comp423-go"
* Next install Dev Containers extension by clicking the boxes on the left control bar and searching "Dev Containers"
* Now create a directory in the root of your project with a file inside by typing ```mkdir .devcontainer```
* Then make a file in that directory called "devcontainer.json" by typing ```code .devcontainer/devcontainer.json```

### 6. Inside that .json file write 
``` { .yaml .copy }
{
    "name": "COMP423 Go",
    "image": "mcr.microsoft.com/devcontainers/go:latest",
    "customizations": {
        "vscode": {
            "settings": {},
            "extensions": ["golang.go"] 
        }
    },
    "postCreateCommand": "go version"
}
```
### To explain what this all means
* name: A name for your dev container
* image: The Docker image to use, in this case, the latest version of a Go environment.
* customizations: This allows you to add useful configurations like extensions and ensure that other developers will have them installed in the dev containers automatically
* postCreateCommand: This is a command to run after the container is created


### 7. Now Reopen the project in a dev container
* You will do this by typing Ctrl+Shift+P and typing "Dev Containers: Reopen in Container" in the search bar above
* After doing that, to ensure you have installed Go type ```go version``` in a new terminal
* You should get something along the lines of ```go version go1.23.4 linux/amd64```

### 8. Creating a Go module 
* To create a go module you will use the subcommand mod 
* You can do this by typing ```go mod init comp423-go```
* This creates and initializes a go module

### 9. Next you will print Hello COMP423!
* To do this you have you first create a go file 
* Go to your root directory and create a new file called "hello.go"
* Then type into that file: 
``` { .yaml .copy }
package main

import "fmt"

func main() {
    fmt.Println("Hello COMP423")
}
```
* After you've done that you will type Ctrl+S to save your file and then run your go file by typing ```go run .``` in a new terminal

> [!NOTE]
> If you get a message that says ```hell0.go:1:1: expected 'package', found 'EOF'``` that means you did not save your file (Ctrl+S) so please do that

### 10. run VS build 
* Above we used the command go run which compiled and ran our go file in one shot
* We could have also used the command go build to print the same file only the go build command compiles our go file into a binary file 
* This gives us the option to run the binary file later on hence why it takes two steps to use the build command
* To use the build command you will type ```go build -o hello-file hello.go``` which compiles your hello.go file into a binary file
* Then you will type ```./hello-file``` which will run the compiled binary file and print the message: ```Hello COMP423```

### 11. Finally lets push your work to GitHub!
* To do this you will type ```git add .``` in a new terminal 
* Then type ```git commit -m "Learned how to code in Go!"``` to commit all your work
* Finally type ```git push --set-upstream origin main``` to push your work onto your GitHub repository
* Now when you refresh your browser, you will see your work in your repository!

### Results

#### Go
> I would add your results and a link to your Go repository here
#### Rust
>I would add your results, a link to my tutorial, and a link to your Rust repository here

>*Jordan, Kris "Starting a Static Website Project with MkDocs - COMP423 - Spring 2025" [https://comp423-25s.github.io/resources/MkDocs/tutorial/#step-2-add-requirementstxt-python-dependency-configuration](https://comp423-25s.github.io/resources/MkDocs/tutorial/#step-2-add-requirementstxt-python-dependency-configuration) 2025, January 17*

