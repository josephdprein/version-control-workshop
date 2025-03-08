# Introduction to Version Control: Git and Github

The full text of this talk can be found here: [https://josephdprein.github.io/version-control-workshop/]

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

- Track changes over time and who made them
- Collaborate with others without overwriting each other's work
- Experiment with new features without breaking working code

## Installing Git
Git can be installed on all major operating systems. Follow the steps for your platform:

### Windows: 
- Download from [git-scm.com](https://git-scm.com/download/win)
- Run the installer with default options
- Use Git Bash for command line access

### Mac: 
- Install via Homebrew: `brew install git`
- Or download from [git-scm.com](https://git-scm.com/download/mac)

### Linux: 
- Use package manager: 
  - Ubuntu/Debian: `sudo apt install git`
  - Fedora: `sudo dnf install git`
  - Arch: `sudo pacman -S git`

### Chromebook: 
- Enable Linux (Beta) feature in settings
- Open Terminal and run `sudo apt install git`

### After installation, verify:
  - `git --version` in your terminal/command prompt
  - Configure your identity:
    - `git config --global user.name "Your Name"`
    - `git config --global user.email "your.email@example.com"`

## Your First Repository
A Git repository is a project folder that Git tracks changes for.

Create a new folder and change into it:
```bash
mkdir my-first-repo && cd my-first-repo
```

Initialize a new git repository:
```bash
git init
```

- `git init` creates a new repository
   - Creates a hidden .git folder to track changes
   - Every folder with a .git folder is a Git repository
   - A repository (repo) is just a project tracked by Git

## The Git Workflow

1. **Make Changes**: Edit your files as normal
   - Create, modify, or delete files in your project directory
   - Git tracks the state of your files, but doesn't automatically save changes

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
- It gives you control over exactly what gets committed and when
- It allows you to group related changes together
- It creates a clear history of your project's development

## Cheat Sheet - Essential Commands
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

## Your First Commit

First, create a new file called `helloWorld.html`
Add the following contents and save the file:
```html
<html>
  <body>
    Hello, world!
  </body>
</html>
```

Run `git status`.
Git reports that the file `helloWorld.html` is "untracked", meaning that the changes aren't being monitored by git yet.  
You can track it by running `git add helloWorld.html`. You'll have to do this with any new files you add to your repository.  

Now, commit your changes by running `git commit -m "Add hello world file"`.
Run `git status` once more; git will report nothing has changed since your last commit.
You can see a history of your commits with `git log`.

## Branching
Branches allow you to work on different versions of your code simultaneously.

Let's make a new branch. We can call it whatever we want; how about "add-name"?
The name should ideally be descriptive of the changes you're going to make.
Run `git branch add-name` to create the new branch.

Switch to your new branch with `git checkout add-name`.

Now, let's make changes to our text file.
Replace the word "world" with your name. 
While you're at it, add something new on another line:
```html
<html>
  <body>
    Hello, Joseph!
    Here's an extra sentence.
  </body>
</html>
```

Now, run `git status` again.
It says we have 'changes not staged for commit';
git recognizes that our files have changed, but says we haven't told it to do anything about it yet.

Run `git add helloWorld.html` to stage your changes.
Run `git diff --staged` to see the difference between your last commit and what you have staged.
Now, run `git commit -m "Added my name and more content to helloWorld.html`.

## Merging
Merging integrates changes from one branch into another.

Check out our original branch with `git checkout main`.
Notice that your `helloWorld.html` file is back as it was originally.

Merge your new branch into main with `git merge add-name`.

Now, our `main` branch has our changes from the other branch folded in.


## GitHub 
GitHub is a cloud-based service that hosts Git repositories.

- It allows for easy collaboration and sharing of code
- Provides additional features like issue tracking, creating and reviewing pull requests, and project management

## Making an Account

Go to [github.com](github.com) and sign up for a free account.
Choose a username; it should be one you're comfortable sharing professionally.
Set up your profile with a photo and bio, if you want.

## Forking a repository
Forking creates your own copy of someone else's repository.

You can make changes to your fork without affecting the original.

Your fork remains connected to the original repository; you can pull their changes into your fork when they update the code, or even open a pull request to ask them to fold *your* changes back into *their* code.

Let's fork my sample github pages repository; it contains the text of this talk!
You can find it at [https://github.com/josephdprein/version-control-workshop].
Click 'Fork' in the top right to create your own copy of the repository.

## Setting Up GitHub Pages
GitHub Pages lets you host websites directly from your repository.

To enable GitHub Pages:
  1. Go to your repository on GitHub
  2. Click on "Settings" tab
  3. Scroll down to "GitHub Pages" section
  4. Under "Source", select "main" branch
  5. Click "Save"

- Your site will be published at [https://yourusername.github.io/version-control-workshop/]
- Any changes pushed to the `main` branch will automatically update your live site

## Cloning a repository
Cloning downloads a repository to your local machine.

When you forked this repository in the previous step, it made a copy of it on your own github.
From the page of your fork, click the 'Code <>' dropdown button and copy the URL.
Clone the repo to your computer by running `git clone <URL>` , replacing `<URL>` with the URL you copied.

## Making changes
After cloning a repository, you can modify files and track those changes:

- Personalize the site; delete all this text and add some of your own!
- Test your changes locally by opening the HTML file in a browser
- Stage your changes with `git add`
- Commit your changes with a descriptive message

## Pushing to Remote
Pushing uploads your local commits to GitHub:

- Push your changes to GitHub with `git push origin main`
- Your changes should immediately be visible on your GitHub repository
- You can continue to make changes, commit, and push as needed

## Common Mistakes and How to Fix Them
Everyone makes mistakes with Git. Here are solutions to common problems:

- **Need to undo a commit, but keep the changes**
  - `git reset --soft HEAD~1` removes the commit but keeps changes staged
  - Useful when you want to add more changes to a work-in-progress commit

- **Need to completely undo a commit and all changes**
  - `git reset --hard HEAD~1` removes the commit AND all changes
  - Be careful! This permanently deletes your work.
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

- **Committed to the wrong branch**
  - Use `git log` to identify the commit
  - `git reset --soft HEAD~1` to undo the last commit but keep changes staged
  - `git checkout correct-branch` to switch to the right branch
  - `git commit -m "message"` to commit on the correct branch


