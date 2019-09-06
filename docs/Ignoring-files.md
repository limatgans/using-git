## Ignoring files

Sometimes you might not want git to track certain files (for example compressed files like .rar). To do that, create a `.gitignore` file and add exceptions there.

Here's an example of a .gitignore file that ignores compressed files with extensions (such as .rar, .zip etc)

```
*.7z
*.dmg
*.gz
*.iso
*.jar
*.rar
*.tar
*.zip
```

In case if you wanted a *predefined template* head to [gitignore.io](http://gitignore.io/) and search for your programming lanugage, ide and OS

Alternatively you can also head to [github/gitignore](https://github.com/github/gitignore) to download gitignore templates

- Previous - [Forking a Repository](./Forking-a-Repository.md) | Next - [Further Reading / Sources](./Further-Reading.md)


-[Back to Main Page](./index.md)