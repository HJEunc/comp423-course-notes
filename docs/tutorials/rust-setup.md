# Setting up a dev container for Rust

* Primary author: [Harrison Enyeart](https://github.com/HJEunc)
* Reviewer: [John Shanahan](https://github.com/JoeShans21)

----

## Prerequisites

Before you begin, make sure you have the following installed:

* [Git](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git)
* [Docker](https://www.docker.com/products/docker-desktop)
* [VS Code](https://code.visualstudio.com/) (with the [Dev Containers Extension](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers))
!!! Tip
    No software (e.g., Rust) needs to be installed directly on your host machine. All development will happen inside the container.

---

## Step-by-Step Guide

### 1. Create a New Directory

Start by opening your terminal and creating a new directory by running the command below in a location of your choice.
```bash
mkdir rust-dev-container
cd rust-dev-container
```

Next, initialize a new Git repository:
```bash
git init
```

Now create a ```README.md``` file:
```bash
echo "# Rust Dev Container Project" > README.md
```

### 2. Set Up the Dev Container

Inside your project directory, create a ```.devcontainer``` folder:
```bash
mkdir .devcontainer
```

Create a ```devcontainer.json``` file inside ```.devcontainer```:
```bash
touch .devcontainer/devcontainer.json
```

Open the project in Visual Studio Code:
```bash
code .
```


Now that we are inside VS Code, open the ```devcontainer.json``` file from the ```.devcontainer``` folder and add the following content:
```bash
{
    "name": "Rust Dev Container",
    "image": "mcr.microsoft.com/devcontainers/rust:bullseye",
    "customizations": {
        "vscode": {
            "extensions": [
                "rust-lang.rust-analyzer"
            ]
        }
    }
}
```

!!! Tip
    - This configuration uses the Rust base image provided by Microsoft.
    - The rust-analyzer extension adds helpful features like autocompletion and error highlighting.

Save the file and reopen the project in the Dev Container:

* When prompted, click Reopen in Container in VS Code.

### 3. Verify Rust Installation
Inside the Dev Container terminal, make sure Rust is installed and up to date by running:
```bash
rustc --version
```
You should see an output like:
```bash
rustc 1.84.0 (e4e7dcdcd 2025-01-09)
```
!!! Tip
    If the version is outdated, rebuild the container to ensure the latest image is used.

### 4. Create a Rust Project
Use Cargo to create a new Rust binary project, I'll call mine ```hello-comp423:```
```bash
cargo new hello-comp423 --vcs none
```
!!! Tip
    The --vcs none flag prevents Cargo from initializing another Git repository.

Navigate into the project folder:
```bash
cd hello-comp423
```

### 5. Write Your Program
Open ```src/main.rs``` in VS Code and replace the default content with the following code:
```rust
fn main() {
    println!("Hello, COMP423!");
}
```

!!! Tip
    The println! macro is used in Rust to print text to the console.

### 6. Compile and Run the Program
Compile the program:
```bash
cargo build
```

Run the program:
```bash
cargo run
```

You should see the following output:

```bash
Hello, COMP423!
```

---

## Conclusion
It's that easy. You just successfully set up a Rust development environment in a Dev Container, created a project, and ran your first program.