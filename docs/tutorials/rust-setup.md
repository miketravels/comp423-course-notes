# Setting up a dev container for Rust

* Primary author: [Michael Pearce-Ros](https://github.com/miketravels)
* Reviewer: [Jake Deng](https://github.com/jakethellama)

Welcome to the wonderful world of Rust! This tutorial will show you how to set up a gitHub repository, an development enviroment running Rust, and writing and building a Rust program that says "Hello COMP423". Set up for intializing a git repository and Docker image has been adapted from [the COMP423 - Spring 2025 website.](https://comp423-25s.github.io/resources/MkDocs/tutorial/)

# Pre-requisites
Before getting started, make sure you have the following installed:

* VSCode
* Docker
* Git

# Part 1. Project Setup: Creating the Repository
## Step 1. Create a Local Directory and Initalize Git
(1) Open up terminal or command prompt.

(2) Create a new directory for your project using: 
```
mk dir comp423-hello-rust
cd comp423-hello-rust
```
(3) Initalize a new Git repository

(4) Create a README file:
```
echo "# COMP423 Rust Tutorial" > README.md
git add README.md
git commit -m "Initial commit with README"
```

## Step 2. Create a Remote Repository on GitHub
(1) Log in to your GitHub account and navigate to the Create a New Repository page.

(2) Fill in the details as follows:

* **Repository Name**: ```comp423-hello-rust```

* **Description**: "A program written in Rust that outputs "Hello COMP423" to the console.

* **Visibility**: Public

(3) Do not initzlize the repository with a README, .gitignore, or license.

(4) Click **Create Repository**.
 
## Step 3. Link your Local Repository to GitHub
(1) Add the GitHub repository as a remote: 
```git remote add origin https://github.com/<your-username>/comp423-hello-rust.git```

Replace ```<your-username>``` with your GitHub username.

(2) Check your default branch name with ```git branch```. In the event it isn't ```main```, rename it to main using ```git branch -M main```.

(3) Push your local commits to the GitHub repository:

```git push --set-upstream origin main```

(4) In your web browser, refresh your GitHub repository to verify that the local commit has now been pushed to remote.

# Part 2. Setting Up The Development Enviorment
(1) In VS Code, open the ```comp423-hello-rust``` directory. You can do this via **File > Open Folder**.

(2) Install the **Dev Containers** extension for VS Code.

(3) Create a ```.devcontainer diretory``` in the root of your project with the following file inside of this "hidden" confiugration directory:
```.devcontainer/devcontainer.json```

(4) Inside the ```.devcontainer/devcontainer.json``` file, enter the following configuration information:

```
{
  "name": "COMP423 Hello Rust",
  "image": "mcr.microsoft.com/devcontainers/rust:latest",
  "customizations": {
    "vscode": {
      "settings": {},
      "extensions": ["rust-lang.rust-analyzer"]
    }
  }
}
```

This will get the latest Rust image plus rust-analyser for when we run our container.

(4) Reopen the project in the container by pressing Ctrl+Shift+P (or Cmd+Shift+P on Mac), typing "Dev Containers: Reopen in Container," and selecting the option.

(5) After the container has opened, open a new terminal pane within VSCode. In the terminal, run  ``rustc --version``  to verify that you are using the latest version of rust.

## Part 3. Creating a Rust Project
(1) In the terminal, run ```cargo new hello_comp --vcs none```. This will create a new Rust project. In VS Code's explorer, open up ```main.rs``` under ```hello_comp/main.rs```. 

!!! note
    If the ```hello_comp``` folder does not appear in the explorer after running the cargo command, refresh the explorer.

(2) ```main.rs``` should be preopulated with the following:
```
    fn main() {
        println!("Hello COMP423");
    }
```
 Change the ```println statement``` to  ```println!("Hello COMP423")```. Save the file afterwards.

 (3) In the VSCode terminal, run the ```cd hello_comp``` to enter the project folder. Then run the following to compile and run your program.
 ```
    cargo build
    ./target/debug/hello_comp
 ```

 ```cargo build``` is the Rust equivalent to C's ```gcc``` command, in which it compiles a file to be executed later. Compiled Rust files can be found under ```./target/debug ```. Running ```./target/debug/hello_comp``` will executed the compiled ```hello_comp``` file.

!!! note
    `cargo run` can be used instead to compile and run the program in a single step. It can also accept most arguments that can be used with `cargo build`

# Part 4. Deployment

(1) Enter ```cd ..``` into the terminal to go back to the ```hello_comp``` directory.

(2) Add, commit, and push changes:
```
git add .
git commit -m "Wrote a hello comp423 program in Rust"
git push origin main
```

# Conclusion
With pushing your files to your GitHub repository, you have successfully completed this tutorial!