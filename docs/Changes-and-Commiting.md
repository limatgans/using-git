## Changes and Commiting
Now that you are in your branch, go ahead and make some changes. You can add file or modify existing files. Once you had made you changes, it's time to stage them.

### LifeCyle of a Status of file
When a new file is added it's `untracked`, meaning which your git doesn't have any reference (snapshot) to this file.
The files that Git knows about are called `tracked` files. 
When a existing file inside your repository (`tracked file`) is changed, it's `modified`, meaning which the last snapshot of your file in your git is different from current file.
A `staged` file is when you approve your changes and the file is now ready to be commited. 

![LifeCyle of a status of file](https://git-scm.com/book/en/v2/images/lifecycle.png)

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

> NOTE: By adding files using `git add`, you are staging the files to commit.

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

> NOTE: `git diff` by itself doesn’t show all changes made since your last commit — only changes that are still unstaged. If you’ve staged all of your changes, `git diff` will give you no output.


If you want to see what you’ve staged that will go into your next commit, you can use 

`git diff --staged`

>It's always a good practice to review your changes before you commit

### Commiting Files:
Now it's time to commit the staged files. A commit is equivalent to creating a new snapshot. Note only staged files get commited and modified/untracked files that are not added using `git add` won't be commited. To commit the staged files.

`git commit -m 'commitMessageHere' `

Every commit needs a commit message. It's essential to provide proper message for project management purposes. Follow the commit message process that your team follows. You can also read more on conventional commits [here](https://github.com/conventional-changelog/standard-version#commit-message-convention-at-a-glance) and [here](https://www.conventionalcommits.org/).

You could also skip the entire staging process in case if you wanted to commit all the *modified* files. To do that 

`git commit -a -m 'commitMessageHere' `

> Note: The option -a automatically stage files that have been modified and deleted, but untracked files are not affected.

- Previous - [Creating a branch](./Creating-a-branch.md)  Next - [Pull and Push](./Pull-and-Push.md)


- [Back to Main Page](./index.md)