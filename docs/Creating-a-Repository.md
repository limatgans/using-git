## Creating a Repository

Repository in Git could be considered similar to your project folder that Git could track all the changes happening inside the folder.

Creating a new repository needs you to login to Git repository hosting service such as Github, GitLab, or your own self hosted Git service. Once you have logged in, 

1. Click on 'New Project' button.
2. Provide a Project Name and Project Description (Optional)
3. Choose Visibility option (Public or Private)
4. Press 'Create Project'

> Note: The above steps may be different for some hosted service. It's recommended to read the documentation.

Now that you have created your project, you can either clone the project or initializing a Repository in an Existing Directory

### Configuring the repository
It's better to configure your repository before pushing / commiting. To have a global configuration.

```
git config --global user.name <yourUserName>
git config --global user.email <yourUserEmailId>
```

You can remove the `--global` option to configure just for a particular repository.

### Cloning a repository
Cloning simply means to download the project from *remote server* onto to *your local machine* and start working on it. To clone a repository get the URL of your project found in the project page itself.

There are two ways to clone a repository, one using HTTPS another using SSH

#### Using HTTPS
The `https://` clone URLs are available on all repositories, public and private. These URLs work everywhere--even if you are behind a firewall or proxy. But everytime you do an operation involving remote directory, then you'll be asked for your username and password

Note : The URL should start with `http://` or `https://` and end in `.git` 

Example : https://github.com/ganesh/testProject2.git

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

#### Using SSH
The SSH protocol provides additional security using SSH-keypair and allows you to authenticate to a Git remote server without supplying your username or password each time.

> We won't be covering cloning using SSH here. But if you are interested, then you can follow the [tutorial here](https://help.github.com/en/articles/which-remote-url-should-i-use#cloning-with-ssh-urls)

### Initializing a Repository in an Existing Directory
If you want your repository to be controlled using Git then go to that project’s directory. Open Terminal and type

```
cd existing_folder
git init
```

This creates a new subdirectory named ```.git```. Note we haven't started tracking yet. To track,

```
git remote add origin <gitURL>
git add .
git commit -m "Initial commit"
git push -u origin master
```
- Next - 
- Previous - [Installing GIT](docs/Installing-GIT.md)