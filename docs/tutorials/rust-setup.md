# Setting up a dev container for Rust

* Primary author: [Michael Pearce-Ros](https://github.com/miketravels)
* Reviewer: [Jake Deng](https://github.com/jakethellama)

* Pre-requisites
* VSCode
* Docker
* Git

# Part 1. Project Setup: Creating the Repository
* Step 1. Create a Local Directory and Initalize Git
* (1) Open up terminal or command prompt.
* (2) Create a new directory for your project and enter the directory
* (3) Initalize a new Git repository
* (4) Create a README file:

# Step 2. Create a Remote Repository on GitHub
* (1) Log in to your GitHub account and navigate to the Create a New Repository page.
* (2) Fill in the details as follows:
* (3) Do not initzlize the repository with a README, .gitignore, or license.
* (4) Click Create Repository
 
# Step 3. Link your Local Repository to GitHub
* (1) Add the GitHub repository as a remote:
* (2) Check your default branch name with git branch. In the event it isn't main, rename it to main using git branch -M main.
* (3) Push your local commits to the GitHub repository:
* (4) In your web browser, refresh your GitHub repository to verify that the local commit has now been pushed to remote.

# Part 2. Setting Up The Development Enviorment
* (1) In VS Code, open the comp423-hello-rust directory. You can do this via File > Open Folder.
* (2) Install the Dev Containers extension for VS Code.
* (3) Create a .devcontainer diretory in the root of your project with the following file inside of this "hidden" confiugration directory: .devcontainer/devcontainer.json
* (4) Reopen the project in the container by pressing Ctrl+Shift+P (or Cmd+Shift+P on Mac), typing "Dev Containers: Reopen in Container," and selecting the option.
* (5) After the container has opened, open a new terminal pane within VSCode. In the terminal, run the rustc --version command to verify that you are using the latest version of rust.

# Part 3. Creating a Rust Project
* (1) In the terminal, run 
