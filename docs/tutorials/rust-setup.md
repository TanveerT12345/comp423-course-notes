# Setting up a dev container for Rust

* Primary author: [Tanveer Thethi](https://github.com/TanveerT12345)
* Reviewer: [Abhiraam Aremanda](https://github.com/AbhiraamA)

## Prerequisites 🛠️
Before starting, ensure you have the following installed:

* 🐳 Docker
* 🖥️ [Visual Studio Code](https://code.visualstudio.com/) with the **Dev Containers** extension
* 📂 Git

!!! note
    For more information about installing Docker, refer to the [Docker Documentation](https://docs.docker.com/get-docker/).

---
## Step 1: Initialize a Git Repository 🔧
Start by creating a directory for your project and initializing a Git repository:

| Command                | Description                                          |
|------------------------|------------------------------------------------------|
| `mkdir rust-setup`       | Creates a directory named `rust-setup`.               |
| `cd rust-setup`          | Navigates to the new directory.                     |
| `git init`             | Initializes a Git repository in the current folder. |

Run the following commands in your terminal:

    mkdir rust-setup
    cd rust-setup
    git init

## Step 2: Configure the Dev Container 📦

1. Create a Create a .devcontainer directory:

        mkdir .devcontainer

2. Add the following devcontainer.json file to the .devcontainer folder:

        {  
            "name": "Rust Dev Container",  
            "image": "mcr.microsoft.com/devcontainers/rust:latest",  
            "customizations": {  
                "vscode": {  
                    "extensions": ["rust-lang.rust-analyzer"]  
                }  
            }  
        }  

!!! info
    The rust-lang.rust-analyzer extension is officially maintained by the Rust team. It provides tools like syntax highlighting, autocompletion, and error checking.

## Step 3: Verify Rust Installation 🐹
Once the Dev Container is up and running, check the installed Rust version:

Run in your terminal:

    rustc --version  

You should see output similar to:

    rustc 1.71.0 (abcd1234 2024-01-01)  

!!! note
     Using the Microsoft Rust Dev Container base image ensures you're running the latest stable version of Rust.

## Step 4: Create the Hello 423 Program ✨
Now its time to create your first Rust program

1. Initialize the Rust Project:

        cargo new hello_comp423  
        cd hello_comp423  

2. Directory structure similar to below will be created:

        hello_comp423/  
        ├── Cargo.toml  
        └── src/  
            └── main.rs 

4. Modify the main.rs File

        fn main() {  
            println!("Hello COMP423");  
        }  

## Step 5: Compile and Run the Program 🚀

1. To compile the program into an executable, use the cargo build command::

        cargo build  

    This creates a compiled binary in the target/debug/ directory. Run the following command to execute it:

        ./target/debug/hello_comp423  

    Output:

        Hello COMP423

!!! note
    Think of cargo build like the gcc command in COMP211. It compiles your code but doesn't run it automatically.

## Step 6: Verify and Push 📝

1. Verify the program runs correctly.

2. Push your repository to GitHub:

        git add .  
        git commit -m "Initial Rust setup"  
        git branch -M main  
        git remote add origin <your-repo-url>  
        git push -u origin main  

## Links to Additional Resources 🔗
* [Rust Documentation](https://www.rust-lang.org/learn)
* [MkDocs Documentation](https://www.mkdocs.org/)