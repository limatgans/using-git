## A brief intro to Git Flow
(Taken from `A successful Git branching model by Vincent Driessen` )

Ideally in a Git workflow, there are two main branches - **master** and **develop**

- **master** branch should be used for production ready states
- **develop** branch should have latest delivered development changes

![Develop branch and Master Branch](https://nvie.com/img/main-branches@2x.png)

And rest of the feature branches must be branched from `develop`

![Develop and Feature Branch](https://nvie.com/img/fb@2x.png)

Once a feature branch is completed, it should be merged back to **develop**. After couple of features are merged into develop, it should be tested and should be merged to **master** for production release.
 
> This section is just to give you an intro on a popular Git Workflow. Your team might be using slightly different workflow. Discuss with your team to know more.

![The Git Flow](https://nvie.com/img/git-model@2x.png)

> More on this Git Flow could be found here [A successful Git branching model](https://nvie.com/posts/a-successful-git-branching-model/) 

- Previous - [Pull and Push](./Pull-and-Push.md)   Next - [Merging Branches](./Merging-Branches.md)

- [Back to Main Page](./index.md)