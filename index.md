## Git and GitHub Excercise


### 1. Install Git

First, you can verify whether Git is already pre-installed on your local machine by running below command.

```
git --version
```

This command shows you the current version installed on your local machine.

If no command found, you need to install Git on your local machine from the website [Git Download](https://git-scm.com/downloads) and then try the above command.

### 2. Configure Git

Set local configuration variables. Your username and email address. Git will use this information to identify who made specific changes to files.

```
git config --global user.name "YOUR_USERNAME"
git config --global user.email "YOUR_ID@EXAMPLE.COM"
git config --list
```

### 3. Create and Initialize a Project

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

```ruby
Initialized empty Git repository in /Users/sarathtd/project101/.git/
```

You can run below command to see whether .git sub-directory created.
```
ls -la
```
.git is important sub-directory which stores all the information of repository, tracks all the files & history of a repository. If we remove the directory all the project history will be lost.

### 4. Check the status of our project

```
git status
```

This command gives information on the current status of a git repository and its contents. 

### Basic Concept

There are three states in Git that we need to know about.

1. Working Directory </br>
2. Staging Area — this is where we organize what we want to be committed to the repository </br>
3. Repository — this is our local repo

<p align="center">
<img src="https://user-images.githubusercontent.com/84066151/168658838-469171eb-2991-44ef-ab82-00a149e77d7b.png" width="400">
</p>


### 5. Create new files (simple txt file)

```
touch file1.txt ; echo "i am your first file" > file1.txt
touch file2.txt ; echo "i am your second file" > file2.txt
```

Now you can again check the status of your repository using ```git status``` command.

```ruby
$ git status

On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	file1.txt
	file2.txt
```

### 6. Add files to the Staging Area
```
git add file1.txt file2.txt
```

Then if we run ```git status``` again:
You can now see that files are now pushed into the staging area ready to be committed.

Now both files have been added to the staging area.

```ruby
$ git status

On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
	new file:   file1.txt
	new file:   file2.txt
```

### 7. Removing files from the Staging Area (Unstage)

If you want to remove files from the staging area, you can use the ```git reset``` command. For instance, if you want to remove file1.txt from the staging area:
```
git reset file1.txt
```

If you want to remove all files from the staging area, you can simply type:

```
git reset
```

### 8. Create a Commit to repository

The files we need are in the staging area, let us commit them to the repository using below command.

```
git commit -m "your commit message"
```

- **The commit message should explain what you have changed, which helps other developers working on the project or help you keep track of all the changes.**

- **Make sure your message makes sense for future reference. It is good to be precise on exactly what changes you have made.**

Our first commit


```ruby
$ git commit -m "inital commit"

[master (root-commit) 2d09770] intial commit
 3 files changed, 1 insertion(+)
 create mode 100644 file1.txt
 create mode 100644 file2.txt
 create mode 100644 file3.txt
```

Now run ```git status``` command to find there are any files in the staging area.

```ruby
$ git status

On branch master
nothing to commit, working tree clean
```


### 9. Audit Logs

To check the commits made to the repository, run below command under your working directory

```
git log
```

resposne:

```ruby
commit 2d0977018f0b25821636321fd47001dd0d1cca7a (HEAD -> master)
Author: Sarath TD <sarathtd406@gmail.com>
Date:   Tue May 17 07:44:15 2021 +0530

    intial commit
```

### 10. Undo Last Commit

The ```git log``` command gives the commit hash information which is a unique identifier for each commit. We can use the commit hash and reverted the last commit by running 

Use the revert command to undo changes and revert to a previous commit.

```
git revert [hash]
```


### 11. Create a remote repository in GitHub




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
