# using-git
Using GIT in your workflow

## Table of Contents
1. [What is Git?](#What-is-Git)
2. [Installing Git](#Installing-Git)
3. [Creating a Repository](#Creating-a-Repository)
4. [Creating a branch](#Creating-a-branch)


## What is Git?
In simple terms, **Git** is a *free* and *open source* *distributed* **version control system**.

A **Version Control System (VCS)** manages all the changes to your project and thereby allows you to have track of all the changes by different contributors to your project.

### Central vs Distributed VCS

Central VCS (such as CVS, Subversion, and Perforce) have a single server that contains all the versioned files, and a number of clients that check out files (snapshots) from that central place. One of major downside is failure of the central server with no proper backups. The entire history of the project is gone except whatever single snapshots people happen to have on their local machines

On the other hand, Distributed VCS (such as **Git**, Mercurial, Bazaar or Darcs) fully mirrors the project from server onto the client machine (including the entire history) instead of just snapshots. In case of server failure, any of the client repositories can be copied back up to the server to restore it 

## Installing GIT

### Checking GIT Version
``` git --version ```

Even if it’s already installed, it’s probably a good idea to update to the latest version.

### For Linux
If you’re on Fedora (or any closely-related RPM-based distribution, such as RHEL or CentOS), you can use dnf:

``` $ sudo dnf install git-all ```

If you’re on a Debian-based distribution, such as Ubuntu, try apt:

``` $ sudo apt install git-all```

For other distributions see [Download Git for Linux](https://git-scm.com/download/linux)

### For Windows
Follow any one of the following steps
1. [Using Installer](https://git-scm.com/download/win) or
2. [Git For Windows](https://gitforwindows.org/) or
3. [GitHub Desktop Website](https://desktop.github.com/)

### For MacOS
On Mavericks (10.9) or above you can do this simply by trying to run git from the Terminal the very first time.

Follow any one of the following steps if you don't have git already in your machine,
1. [Using Installer](https://git-scm.com/download/mac) or
2. Install the Xcode Command Line Tools. or
3. [GitHub Desktop Website](https://desktop.github.com/) 

Source: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git

## Creating a Repository

Creating a new repository needs you to login to Git repository hosting service such as Github, GitLab, or your own self hosted Git service. Once you have logged in, 

1. Click on 'New Project' button.
2. Provide a Project Name and Project Description (Optional)
3. Choose Visibility option (Public or Private)
4. Press 'Create Project'

Note: The above steps may be different for some hosted service. It's recommended to read the documentation.

Now that you have created your project, you can either clone the project or initializing a Repository in an Existing Directory

### Configuring the repository
Its better to configure your repository before pushing / commiting. To have a global configuration.

```
git config --global user.name <yourUserName>
git config --global user.email <yourUserEmailId>
```

You can remove the `--global` option to configure just for a particular repository.

### Clonning a repository
Clonning simply means to download the project and start working on it. To clone a repository get the URL of your project found in the project page itself.

Note : The URL should end in .git 
Example : http://github.com/ganesh/testProject2.git

Now on the desired directory, open the terminal and follow the steps to clone.

```
git clone <gitURL>
cd <repositoryName>
touch README.md
git add README.md
git commit -m "add README"
git push -u origin master
```
Now you can start working on your directoy. We will get to add, commit, and push commands later in this document.

### Initializing a Repository in an Existing Directory
If you want your repository to be controlled using Git then go to that project’s directory. Open Terminal and type

```
cd existing_folder`
git init`
```

This creates a new subdirectory named ```.git```. Note we haven't started tracking yet. To track,

```
git remote add origin <gitURL>`
git add .`
git commit -m "Initial commit"`
git push -u origin master`
```


## Creating a branch

### Branches
In simplest terms, branching allows you to seperate from the main line (with entire history of project at that point) so that your further development doesn't disturb other works. Branching is a crucial part in several VCS. A major advantage of Git is that branching operations are lightweight thereby making them superfast. 

The default branch in a Git repository is ```master```

### Listing the branches in a project
To get the list of all the branches in your repository.
```git branch```

### Creating a new branch
Now that we have created a repository, let's create a new branch. On your terminal, 

```git branch <branchName>```

This creates a new branch, but you are still in master branch (In Git terminology your HEAD is still pointing to master branch).

To shift/move the HEAD to the new branch we just created,

```git checkout <branchName>```

Alternatively, you can combine both the commands as follows

``` git checkout -b <branchName>```

This creates the branch and checkouts(points the HEAD) to it immediately.

## Changes and Commiting
Now that you are in your branch, go ahead and make some changes. You can add file or modify existing files. Once you had made you changes, it's time to stage them.

### LifeCyle of a status of file
When a new file is added it's `untracked`, meaning which your git doesn't have any reference (snapshot) to this file.
The files that Git knows about are called `tracked` files. 
When a existing file inside your repository (`tracked file`) is changed, it's `modified`, meaning which the last snapshot of your file in your git is different from current file.
A `staged` file is when you approve your changes and the file is now ready to be commited. 

![LifeCyle of a status of file](https://git-scm.com/book/en/v2/images/lifecycle.png)
Format: ![Alt Text](Figure:LifeCyle-of-a-status-of-file)

### Knowing the Status of Your Files
Running `git status` would let you know the status of your file

If you run `git status` immediately after clone, you would find something like this

```
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```

Lets say we create a new file 'CONTRIBUTING.md'. Upon running `git status`

```
$ echo 'My Project by me' > CONTRIBUTING.md
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Untracked files:
  (use "git add <file>..." to include in what will be committed)

    CONTRIBUTING.md

nothing added to commit but untracked files present (use "git add" to track)
```

### Staging Files

To track the changes use
`git add .`

To add only particular files
`git add <fileName>`

> NOTE: By adding files, you are staging the files to commit.

```
$ git add CONTRIBUTING.md
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

    new file: CONTRIBUTING.md
```

To see what you’ve changed but not yet staged,

`git diff`

> NOTE: `git diff` by itself doesn’t show all changes made since your last commit — only changes that are ?> still unstaged. If you’ve staged all of your changes, `git diff` will give you no output.


If you want to see what you’ve staged that will go into your next commit, you can use 

`git diff --staged.`

### Commiting Files:
Now it's time to commit the staged files. A commit is equivalent to create a new snapshot. Note only staged files get commited and modified/untracked files that are not added using `git add` won't be commited. To commit the staged files.

`git commit -m 'commitMessageHere' `

Every commit needs a commit message. It's essential to provide proper message for project management purposes. Follow the commit message process that your team follows. You can also read more on conventional commits [here](https://github.com/conventional-changelog/standard-version#commit-message-convention-at-a-glance) and [here](https://www.conventionalcommits.org/).

You could also skip the entire staging process in case if you wanted to commit all the changes you had made. To do that 

`git commit -a -m 'commitMessageHere' `


## Further Reading / Sources:
1. [Git-Branching: Branches in a Nutshell](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell)