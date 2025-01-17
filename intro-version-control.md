# Git Version Control

## Table of Contents
* [Explanation of version control](#Explanation-of-version-control)
* [Setting up git](#Setting-up-git)
* [Creating a repository](#Creating-a-repository)
* [Tracking changes](#Tracking-changes)
* [Creating branches](#Creating-branches)
* [Cloning repositories](#Cloning-repositories)
* [References](#References)
* [Further reading](#Further-reading)

## Explanation of version control
### Objectives

- Understand the benefits of an automated version control system.
- Understand the basics of how automated version control systems work.

### Tutorial steps

Version control systems are tools that keep track of changes to documents. There are
many benefits to using version control systems, including:

- Having a complete change history for all files
- Collaborating effectively through branching and merging
- Relating changes to project management goals

Version control systems are most commonly used for code, but are useful for many
other tasks such as writing papers, proposals, and presentations.

## Setting up git

### Objectives

- Configure `git` the first time it is used on a computer.
- Understand the meaning of the `--global` configuration flag.

### Tutorial steps

In this section, we will configure some Git settings.

1. Open terminal (macOS) or Git Bash (windows).
2. Set your name:

    `git config --global user.name "Your name"`
3. Set your email (see note below for instructions to keep your email private):

    `git config --global user.email "Your email"`
4. Set your preferred line endings:

    `git config --global core.autocrlf input` (macOS)

    `git config --global core.autocrlf true` (windows)
5. Set your preferred text editor (See
  [git-scm Appendix C](https://www.git-scm.com/book/en/v2/Appendix-C%3A-Git-Commands-Setup-and-Config)
  for options):

    `git config --global core.editor "editor name"`

6. Set a default branch name:

    `git config --global init.defaultBranch main`
7. Check your settings:

    `git config --list`
    
    `git config user.name`

> **NOTE**: If you wish to use a private email with GitHub, then you can use the format
> `git config --global user.email username@users.noreply.github.com`, where `username` is
> replaced by your GitHub username.

Many other settings are [configurable in Git](https://www.git-scm.com/book/en/v2/Customizing-Git-Git-Configuration).
You can also get help using `git config --help`.

## Creating a repository

### Objectives

- Create a local Git repository.
- Describe the purpose of the `.git` directory.

### Tutorial steps

In this section, we will create a repository.

1. Create a directory in the `Desktop` folder:

    ```
    cd ~/Desktop
    mkdir learn-git
    cd learn git
    ```

2. Tell Git to make `learn-git` a repository:

    `git init`

3. View the new `.git` hidden directory created by Git:

    `ls -a`
4. Check the status of the Git repository:

    `git status`

## Tracking changes

### Objectives

- Complete the modify-add-commit cycle.
- Understand how to write descriptive commit messages.

### Tutorial steps

1. Check that you are in the current directory:

    `pwd`

2. Create a file that contains some notes:

    `code git-notes.txt`
3. Type text into `git-notes.txt` and save the file.
4. In the terminal, check that `git-notes.txt` contains some content:

    `cat git-notes.txt`
5. Check the status of the project:

    `git status`

6. Tell Git to track the file using `git add`:

    `git add git-notes.txt`
7. Check the status of the project:

    `git status`
8. Commit the changes to the git repository:

    `git commit -m "Start notes on Git"`
9. Check the status of the project:

    `git status`
10. Review the changes using `git log`:

    `git log`

> **Note**: [Chris Beam's blog](https://chris.beams.io/posts/git-commit/) includes a
> great guide on how to write useful commit messages.

### Exercises

- Create a new file `more-notes.txt`, add text to the file, and commit it to your
  repository.
- Edit both `git-notes.txt` and the new file, stage the changes, and commit them to your
  repository using a single commit.


## Creating branches

### Objectives

- Understand the basics of branching in Git.
- Create a branch and check it out.
- Return to the main branch after committing changes to the new branch.

### Tutorial steps

Branching provides a way to develop independent from the main development line.

1. Use the `git branch` to create a new branch:

    `git branch test-branch`

2. Use `git branch` to view the branches in the repository:

    `git branch`

2. Checkout your new branch:

    `git checkout test-branch`

3. Follow the lessons from [tracking changes](#tracking-changes) to commit a new file
   `test-branch.txt`.
4. Checkout the main branch and note what happens to the file:

    `git checkout main`
5. Merge your changes into the main branch using `git merge`:

    `git merge test-branch`

## Cloning repositories

The `git clone` command is used to create a copy of a specific repository or branch.
Here we will clone the repository for the MATLAB portion of this workshop:

1. Navigate to the folder that you want to repository to be located inside:

    ```
    cd ~/Desktop
    mkdir workshops
    cd workshops
    ```
2. Clone the remote remote repository for this workshop:

    `git clone https://github.com/meghanrjones/2021-reu-matlab-git.git`

## References

- This tutorial was adapted from Software Carpentry's [Version Control with Git](http://swcarpentry.github.io/git-novice/).

## Further reading

- [Pro Git](https://www.git-scm.com/book/en/v2) book.
- [Atlassian Git tutorials](https://www.atlassian.com/git/tutorials).