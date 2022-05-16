## Welcome Git Handson Excercise


### Install Git

First, you can verify whether Git is already pre-installed on your local machine by running below command.

```
git --version
```

This command shows you the current version installed on your local machine.

If no command found, you install Git on your local machine from the website [Git Download](https://git-scm.com/downloads) and then try the above command.

### Configure Git

Set local configuration variables. Your username and email address. Git will use this information to identify who made specific changes to files.

```
git config --global user.name "YOUR_USERNAME"
git config --global user.email "YOUR_ID@EXAMPLE.COM"
git config --list
```

### Create and Initialize a Project

create a project directory "project101"
```
mkdir project101
cd project101
```

Before we can do anything git-related, we must initialize a repo first!. This is something you do once per project. Initialize the repo in the top-level folder containing the project.

Now to initialize your project, simply run
```
git init
```
This will tell Git to get ready to start watching your files for every change that occurs. you will get a response that repository has been initialized: </br>

```diff
- Initialized empty Git repository in /Users/sarathtd/project101/.git/
```

You can run below command to see whether .git sub-directory created.
```
ls -la
```
.git is important sub-directory which stores all the information of repository, tracks all the files & history of a repository. If we remove the directory all the project history will be lost.

### Check the status of our project

```
git status
```

This command gives information on the current status of a git repository and its contents. 


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [Basic writing and formatting syntax](https://docs.github.com/en/github/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/sarathtd406/Git-tutorial-101/settings/pages). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://support.github.com/contact) and we’ll help you sort it out.
