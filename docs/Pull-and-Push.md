## Pull and Push
Now that we have commited our changes, it's time to push the changes to the server. Note that the commit you just made is still in your local machine. By pushing it we would let the server know about the local changes we had commited.

> It's always a good practice to `pull` first before you `push` to avoid any conflicts.

### Pull from a branch
By pull, you are downloading the latest snapshot of git to your local machine.
If you don't have any branches, you can simply use
`git pull`

But here, we are in a branch other than `master`. We need to pull latest snapshot of this branch, hence

`git pull origin <branchName>`

Once we have sucessfuly pulled without any conflicts, we are ready to push our commits.

### Pushing to a branch
If you don't have any branches, you can simply use
`git push`

If we need to push to a particular branch

`git push origin <branchName>`

- Next - [A brief intro to Git Flow](./A-brief-intro-to-Git-Flow.md)
- Previous - [Changes and Commiting](./Changes-and-Commiting.md)   

- [Back to Main Page](./index.md)