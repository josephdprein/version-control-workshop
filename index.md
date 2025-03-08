# Introduction to Version Control: Git and Github

## Table of Contents
- [Motivations](#motivations)
- [Git](#git)
  - [Installation](#installation)
  - [Your First Repository](#your-first-repository)
  - [The Git Workflow](#the-git-workflow)
  - [Cheat Sheet - Essential Commands](#cheat-sheet---essential-commands)
  - [Your First Commit](#your-first-commit)
  - [Branching](#branching)
  - [Merging](#merging)
- [GitHub](#github)
  - [Making an Account](#making-an-account)
  - [Forking a repository](#forking-a-repository)
  - [Cloning a repository](#cloning-a-repository)
  - [Making changes](#making-changes)
  - [Pushing to Remote](#pushing-to-remote)
  - [Setting Up GitHub Pages](#setting-up-github-pages)
- [Common Mistakes and How to Fix Them](#common-mistakes-and-how-to-fix-them)

## Motivations
Version control systems like Git solve several common problems in software development:

- Version control helps track changes over time
- Enables collaboration with others without overwriting each other's work
- Provides a history of all changes and who made them
- Allows you to experiment with new features without breaking working code

## Git

### Installation
Git can be installed on all major operating systems. Follow the steps for your platform:

- Windows: 
  - Download from [git-scm.com](https://git-scm.com/download/win)
  - Run the installer with default options
  - Opens Git Bash for command line access

- Mac: 
  - Install via Homebrew: `brew install git`
  - Or download from [git-scm.com](https://git-scm.com/download/mac)
  - Terminal provides access to Git commands

- Linux: 
  - Use package manager: 
    - Ubuntu/Debian: `sudo apt install git`
    - Fedora: `sudo dnf install git`
    - Arch: `sudo pacman -S git`

- Chromebook: 
  - Enable Linux (Beta) feature in settings
  - Open Terminal and run `sudo apt install git`
  - Works in the Linux container environment

- After installation, verify with:
  - `git --version` in your terminal/command prompt
  - Configure your identity:
    - `git config --global user.name "Your Name"`
    - `git config --global user.email "your.email@example.com"`



### Your First Repository
A Git repository is a project folder that Git tracks changes for:

- `git init` creates a new repository
- Creates a hidden .git folder to track changes
- Every folder with a .git folder is a Git repository
- A repository (repo) is just a project tracked by Git

### The Git Workflow
Understanding the basic Git workflow is essential for effective version control:

1. **Make Changes**: Edit your files as normal
   - Create, modify, or delete files in your project directory
   - Git tracks the state of your files but doesn't automatically save changes

2. **Stage Changes**: Select which changes to include in your next commit
   - Use `git add <filename>` to stage specific files
   - Use `git add .` to stage all changes
   - Staging is like putting items in a shopping cart before checkout
   - View staged changes with `git status`

3. **Commit Changes**: Create a permanent snapshot of your staged changes
   - Use `git commit -m "Descriptive message"` to save your changes
   - Each commit has a unique identifier (hash)
   - Good commit messages explain why changes were made, not just what changed
   - View commit history with `git log`

This three-step process (edit → stage → commit) is the foundation of Git's power:
- It gives you control over exactly what gets committed
- It allows you to group related changes together
- It creates a clear history of your project's development

### Cheat Sheet - Essential Commands
Here are the most commonly used Git commands you'll need to know:

- `git init` - Create a new repository
- `git status` - Check what files are tracked/changed
- `git add <file>` - Stage changes for commit
- `git commit -m "message"` - Save staged changes
- `git log` - View history of commits
- `git branch` - List branches
- `git checkout <branch>` - Switch to a branch
- `git merge <branch>` - Combine branches

For complete documentation, visit [git-scm.com](https://git-scm.com/doc)

### Your First Commit
Making your first commit involves tracking a file and saving its state:

*After each of these steps, run 'git status' to see what git reports.*

- Create a simple text file; 'helloWorld.html'
- Track it with `git add helloWorld.html`
- Commit it with `git commit -m "Add hello world file"`
- View your commit with `git log`

### Branching
Branches allow you to work on different versions of your code simultaneously:

- Make a branch off of main called `feature/add-name` with `git branch feature/add-name`
- Switch to your new branch with `git checkout feature/add-name`
- Change the text file to say 'Hello, {your name}!'
- Stage and commit your changes
- Branches let you work on features without affecting the main code

### Merging
Merging integrates changes from one branch into another:

- Merging combines the history of two branches
- Check out main with `git checkout main`; notice it is unchanged
- Merge your new branch into main with `git merge feature/add-name`
- Notice that main now has your new changes

## GitHub 
GitHub is a cloud-based service that hosts Git repositories:

- GitHub is a web platform for hosting Git repositories
- It allows for easy collaboration and sharing of code
- Provides additional features like issue tracking, creating and reviewing pull requests, and project management

### Making an Account
Creating a GitHub account is the first step to using the platform:

- Go to github.com and sign up for a free account
- Choose a username that you're comfortable sharing professionally
- Set up your profile with a photo and bio, if you want

### Forking a repository
Forking creates your own copy of someone else's repository:

- You can make changes to your fork without affecting the original
- Forking is common for contributing to open source projects
- Your fork remains connected to the original repository
- Fork my sample github pages repository (link to be added later)

### Cloning a repository
Cloning downloads a repository to your local machine:

- Clone the repo locally with `git clone <URL>` so you can make changes
- The clone includes all files, branches, and history
- Your clone is connected to the remote repository on GitHub

### Setting Up GitHub Pages
GitHub Pages lets you host websites directly from your repository:

To enable GitHub Pages:
  1. Go to your repository on GitHub
  2. Click on "Settings" tab
  3. Scroll down to "GitHub Pages" section
  4. Under "Source", select "main" branch
  5. Click "Save"

- Your site will be published at https://yourusername.github.io/repository-name/
- Any changes pushed to main will automatically update your live site
- GitHub Pages works best with HTML, CSS, and JavaScript files
- You can also use [Jekyll](https://jekyllrb.com/docs/) for more advanced static sites

### Making changes
After cloning a repository, you can modify files and track those changes:

- Personalize the site by editing the HTML/CSS files
- Test your changes locally by opening the HTML file in a browser
- Stage your changes with `git add`
- Commit your changes with a descriptive message

### Pushing to Remote
Pushing uploads your local commits to GitHub:

- Push your changes to GitHub with `git push origin main`
- Your changes are now visible on your GitHub repository
- GitHub will display your updated code automatically
- You can continue to make changes, commit, and push as needed

## Common Mistakes and How to Fix Them
Everyone makes mistakes with Git. Here are solutions to common problems:

- **Committed to the wrong branch**
  - Use `git log` to identify the commit
  - `git reset --soft HEAD~1` to undo the last commit but keep changes staged
  - `git checkout correct-branch` to switch to the right branch
  - `git commit -m "message"` to commit on the correct branch

- **Need to undo a commit but keep the changes**
  - `git reset --soft HEAD~1` removes the commit but keeps changes staged
  - Useful when you want to amend a commit message or add more files

- **Need to completely undo a commit and all changes**
  - `git reset --hard HEAD~1` removes the commit AND all changes
  - Be careful! This permanently deletes your work
  - Use `git reflog` if you need to recover deleted commits

- **Need to undo a commit but keep a record**
  - `git revert <commit-hash>` creates a new commit that undoes changes
  - Safer for shared branches since it doesn't alter history
  - Good practice for collaborative work

- **Added the wrong files to staging**
  - `git reset <file>` to unstage specific files
  - `git reset` to unstage all files

- **Accidentally deleted a file**
  - `git checkout -- <file>` to restore a deleted file from the last commit
