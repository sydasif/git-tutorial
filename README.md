# A Beginner Guide to Git

Git is a version control system, used to track versions of a file, and helps collaborate with developers and work in a team.

It's decentralized in nature, helping the larger team to work together. Every developer has their own copy of the repository on their machine, they can locally work without the internet on their machine and commit their changes.

Once their work is done they can publish their changes on a remote git repository and share them with other developers.

You can also do a hands-on exercise(using GitHub) to practice git along with this thread as well.

Pre-requisite:

[Install Git](https://git-scm.com/downloads)

[Create an Account on GitHub](https://wikihow.com/Create-an-Account-on-GitHub)

[Create a repo](https://docs.github.com/en/get-started/quickstart/create-a-repo)

## git init

It initializes an empty repository as a git repository on your local machine.

As shown below, We've created an empty folder - `my-repo` and run the `git init` command to mark it as a git repository.

```console
[$] <> my-repo>git init
Initialized empty Git repository in ~/my-repo/.git/
```

Let's add an empty file - "script.js" in this local git folder - `my-repo`.

```console
[$] <> ~/my-repo (main)
$ ls
script.py
```

## git status

git status will show a list of all files along with their status.
Newly added files will be "untracked" by git initially.

It is the most frequent command we will use to see file status.

As shown below in the untracked file list we can see "script.py"

```console
[$] <> ~/my-repo (main)
$ git status 
On branch main

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)
        script.py

nothing added to commit but untracked files present (use "git add" to track)
```

## git add

Out of all the untracked files, we can pick which file we want to commit. This is called staging. 

Use Below Command to stage a file:
`git add <file>`.

Below we've added `script.py` to the stage and then used git status to check its status.

```console
[$] <> ~/my-repo (main)
$ git add script.py 

[$] <> ~/my-repo (main)
$ git status
On branch main

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   script.py
```

## git commit

Now, its time to commit the file to our local repository using 
`git commit -m <commit-message>`

Below we've committed the "script.js" file with a commit message.
Then we've used git status to see if our commit is successful or not.

```console
[$] <> ~/my-repo (main)
$ git commit -m "first commit"
[main (root-commit) 2664303] first commit
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 script.py

```

So far, we've committed the above file in our local repository only. Now it's time to push this file to remote repo.

If you remember, I've asked you to create a repo on GitHub in the prerequisite section. Now it's time to use it. Please get the link to your remote branch ready.

## git remote

Before sending our code to a remote repository, we need to map our local repo with equivalent remote repo by using the below command:

`git remote add origin <remote-repo-url>`

As shown below:

```console
[$] <> ~/my-repo (main)
$ git remote add origin git@github.com:sydasif/my-repo.git
```

## git push

At last, using the below push command we can send our file to the remote repo.

`git push origin <remote-branch-name>`

As shown below:

```console
[$] <> ~/my-repo (main)
$ git push -u origin main
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 210 bytes | 105.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To github.com:sydasif/my-repo.git
 * [new branch]      main -> main
branch 'main' set up to track 'origin/main'.

```

This was part 1 in the Git.
