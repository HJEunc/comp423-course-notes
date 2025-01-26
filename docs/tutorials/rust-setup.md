# Setting up a dev container for Rust

* Primary author: [Harrison Enyeart](https://github.com/HJEunc)
* Reviewer: [John Shanahan](https://github.com/JoeShans21)

----

## Prerequisites

Before you begin, make sure you have the following installed:

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

Now create a README.md file:
```bash
echo "# Rust Dev Container Project" > README.md
```

### 2. Set Up the Dev Container