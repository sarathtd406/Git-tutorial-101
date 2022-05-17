## Git and GitHub Basics

### Adding locally hosted code to GitHub
#### Learn how to add existing source code or repositories to GitHub from the command line using GitHub CLI or Git Commands. Then, share your code and invite others to work with you.

#### Let's get started !!

### 1. Install Git

First, you can verify whether Git is already pre-installed on your local machine by running below command.

```
$ git --version
```

This command shows you the current version installed on your local machine.

If no command found, you need to install Git on your local machine from the website [Git Download](https://git-scm.com/downloads) and then try the above command.

### 2. Configure Git

Set local configuration variables. Your username and email address. Git will use this information to identify who made specific changes to files.

```
$ git config --global user.name "YOUR_USERNAME"
$ git config --global user.email "YOUR_ID@EXAMPLE.COM"
$ git config --list
```

### 3. Create and Initialize a Project

create a project directory "project101"
```
$ mkdir project101
$ cd project101
```

Before we can do anything git-related, we must initialize a repo first!. This is something you do once per project. Initialize the repo in the top-level folder containing the project.

Now to initialize your project, simply run

```
$ git init -b main
```
This will tell Git to get ready to start watching your files for every change that occurs. you will get a response that repository has been initialized:

```ruby
Initialized empty Git repository in /Users/sarathtd/project101/.git/
```

You can run below command to see whether .git sub-directory created.

```
$ ls -la
```

**.git is important sub-directory which stores all the information of repository, tracks all the files & history of a repository. If we remove the directory all the project history will be lost.**

### 4. Check the status of our project

To see the current status of a git repository and its contents, use below command.

```
$ git status
```

### Basic Concept

There are three states in Git that we need to know about.

1. Working Directory 
2. Staging Area — this is where we organize what we want to be committed to the repository
3. Repository — this is our local repo

<p align="center">
<img src="https://user-images.githubusercontent.com/84066151/168658838-469171eb-2991-44ef-ab82-00a149e77d7b.png" width="400">
</p>


### 5. Create new files (simple txt file)

Create file1.txt and file2.txt with some content in it.

```
$ touch file1.txt ; echo "i am your first file" > file1.txt
$ touch file2.txt ; echo "i am your second file" > file2.txt
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

Use git add to add specific files to the staging area. Separate files with spaces to add multiple at once. 

This command is a way of telling Git, "please include this change in our next commit"

```
$ git add file1.txt file2.txt
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

#### Removing files from the Staging Area (Unstage)

If you want to remove files from the staging area, you can use the ```git reset``` command. For instance, if you want to remove file1.txt from the staging area:
```
$ git reset file1.txt
```

If you want to remove all files from the staging area, you can simply type:

```
$ git reset
```

### 7. Create a Commit to repository

The files we need are in the staging area, let us commit them to the repository using below command. This Commits the tracked changes and prepares them to be pushed to a remote repository.

```
$ git commit -m "your commit message"
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
$ git log
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
$ git revert [hash]
```

## >> Quick Summary on git commands used

```
git --version
git config
git init
git status
git add
git reset
git commit
git log
git revert
```

## GitHub

**Till now we learnt how to create a local repository, initialize repository, add files and commit to the repository.**

**Next, we will learn how to share a repository with other developers. We can do this using GitHub hosting service.**
**GitHub allows you to keep track of your code when you're working with a team and need to modify the project's code collaboratively.**


### 11. Create a New Repository on GitHub

Follow below steps to create a new repository on GitHub:

1. Log in GitHub. Click on the **+** icon next to your profile picture, in the top right corner and select **New repository**

<p align="center">
   <img width="310" alt="image" src="https://user-images.githubusercontent.com/84066151/168719629-dcee84b8-a2c5-455e-8856-81fdc1b22a3b.png">
</p>
	
2. Enter a name for your repository, add description, select private setting and Click on create repository

<img width="742" alt="image" src="https://user-images.githubusercontent.com/84066151/168720314-db424854-a521-4208-b500-8f2918ae8c0f.png">

<img width="738" alt="image" src="https://user-images.githubusercontent.com/84066151/168720393-e1495adc-fe31-4697-880f-1866ac3b1b40.png">


### 12. Configure the GitHub repository in your terminal

Get the REMOTE_URL from GitHub as shown below.

<p align="center">
<img width="406" alt="image" src="https://user-images.githubusercontent.com/84066151/168740828-02058777-d5b6-48f5-823b-46353920a072.png">
</p>

In Terminal, add the URL for the remote repository where your local repository will be pushed. Below command sets the new remote repository.

```
$ git remote add origin  <REMOTE_URL>
```

Below command verifies the new remote repository URL

```ruby
$ git remote -v

origin	https://github.com/sarathtd406/testrepo.git (fetch)
origin	https://github.com/sarathtd406/testrepo.git (push)
```

### 13. Push the changes in your local repository to GitHub.com

Below command pushes the changes in your local repository up to the remote repository you specified as the origin.

```
$ git push -u origin main
```

respose:

```ruby
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 8 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 286 bytes | 286.00 KiB/s, done.
Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/sarathtd406/testrepo.git
 * [new branch]      main -> main
Branch 'main' set up to track remote branch 'main' from 'origin'.

```

### 14. Invite collaborators to your private GitHub repository

1. Log in GitHub. Navigate to your repository and click on **Settings**
2. In the left menu click on **Collaborators**
3. Click on **Add People** button (right side under Manage access)

<img width="1403" alt="image" src="https://user-images.githubusercontent.com/84066151/168744690-16b8b8a6-1537-4f8d-96f3-93351c8f84c6.png">



