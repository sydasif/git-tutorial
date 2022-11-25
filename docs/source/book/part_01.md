# What is version control?

Version control, also known as source control, is the practice of tracking and managing changes to software code. Version control systems are software tools that help software teams manage changes to source code. As development environments have accelerated, version control systems help software teams work faster and smarter.

## Git and GitHub

Git is a distributed version control system (VCS) that maintains a history of changes to files for reference and rolls back a change. It is a software for tracking changes in any set of files, usually used for coordinating work among programmers who are collaborating on the same source code, and widely used, released under GNU GPL v2 license.

It's decentralized in nature, helping the larger team to work together. Every developer has their own copy of the repository on their machine, they can locally work without the internet on their machine and commit their changes.

Once their work is done they can publish their changes on a remote git repository and share them with other developers.

Git can:

- track changes n file
- store multiple versions of the same file
- record who made changes and when

You can also do a hands-on exercise(using GitHub) to practice git along with this chapter as well. At the command line, first verify that you have Git installed.

```console
[$] <> git --version
$ git version 2.37.3.windows.1
```

If nothing is returned, or the command is not recognized, you may have to install Git on your system by downloading and running the installer.

## Pre-requisite

- [Install Git](https://git-scm.com/downloads)
- [Create an Account on GitHub](https://wikihow.com/Create-an-Account-on-GitHub)
- [Create a repo](https://docs.github.com/en/get-started/quickstart/create-a-repo)

## What is GitHub?

GitHub on the other hand the web-based cloud offering of Git. These services use Git in the background to offer a cloud / online repository to store your code securely so that it’s accessible to everyone, no matter where they are and they can collectivity contribute to the same source code. GitHub also has private repositories, the main use of GitHub is to place code for various projects.

## Create your first repository

### git init

It initializes an empty repository as a git repository on your local machine.

As shown below, We've created an empty folder - `git-tutorial` and run the `git init` command to mark it as a git repository.

```console
[$] <> my-repo>git init
Initialized empty Git repository in ~/git-tutorial/.git/
```

This creates a hidden folder, `.git`, which contains the plumbing needed for Git to work.

Let's add an empty file - "script.py" in this local git folder - `git-tutorial`.

```console
[$] <> ~/git-tutorial (main)
$ ls
script.py
```

### git status

git status will show a list of all files along with their status. Newly added files will be "untracked" by git initially. It is the most frequent command we will use to see file status.

As shown below in the untracked file list we can see "script.py"

```console
[$] <> ~/git-tutorial (main)
$ git status 
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        script.py

nothing added to commit but untracked files present (use "git add" to track)
```

Check what files Git will add to your new repository; this step is worth special care.

### git add

Review the resulting list of files; you can tell Git which of the files to place into version control (avoid adding files with confidential information such as passwords, or files that just clutter the repo). Out of all the untracked files, we can pick which file we want to commit. This is called staging.

Use Below Command to stage a file:

```console
[$] <> ~/git-tutorial (main)
git add <file>
```

Below we've added `script.py` to the stage and then used git status to check its status.

```console
[$] <> ~/git-tutorial (main)
$ git add script.py 

[$] <> ~/git-tutorial (main)
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   script.py
```

If all files in the list should be shared with everyone who has access to the repository, a single command will add everything in your current directory and its subdirectories.

```console
[$] <> ~/git-tutorial (main)
$ git add .
```

This will "stage" all files to be added to version control, preparing them to be committed in your first commit. For files that you want never under version control, create and populate a file named `.gitignore` before running the add command.

### git commit

Now, its time to commit the file to our local repository using  `git commit -m <commit-message>`.

Below we've committed the "script.py" file with a commit message. Then we've used git status to see if our commit is successful or not.

```console
[$] <> ~/git-tutorial (main)
$ git commit -m "first commit"
[main (root-commit) 2664303] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 script.py

```

This creates a new commit with the given message. A commit is like a save or snapshot of your entire project. You can now push, or upload, it to a remote repository, and later you can jump back to it if necessary. If you omit the `-m` parameter, your default editor will open and you can edit and save the commit message there. So far, we've committed the above file in our local repository only. Now it's time to push this file to remote repo.

```{Note}
Before adding the remote you have to create the required repository in your git service, You'll be able to push/pull commits after adding your remote.
```

If you remember, I've asked you to create a repo on GitHub in the prerequisite section. Now it's time to use it. Please get the link to your remote branch ready.

### git remote

Before sending our code to a remote repository, we need to map our local repo with equivalent remote repo by using the below command:

As shown below:

```console
[$] <> ~/git-tutorial (main)
$ git remote add origin git@github.com:sydasif/git-tutorial.git
```

The git remote add command takes two arguments:

1. A remote name for example, `origin`
2. A remote URL for example, `https://<your-git-service-address>/user/repo.git`

### git push

At last, using the below push command we can send our file to the remote repo. As shown below:

```console
[$] <> ~/git-tutorial (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 210 bytes | 105.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:sydasif/git-tutorial.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

```

This was part 1 in the Git.
