# 2. Create your first repository

## git init

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

## git status

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

## git add

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

## git commit

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

## git remote

Before sending our code to a remote repository, we need to map our local repo with equivalent remote repo by using the below command:

As shown below:

```console
[$] <> ~/git-tutorial (main)
$ git remote add origin git@github.com:sydasif/git-tutorial.git
```

The git remote add command takes two arguments:

1. A remote name for example, `origin`
2. A remote URL for example, `https://<your-git-service-address>/user/repo.git`

## git push

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
