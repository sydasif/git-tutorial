# 3. Clone a repository

The git clone command is used to copy an existing Git repository from a server to the local machine. If someone else wants to take your changes, add their changes on top of it and push those changes on the remote git repo.

## git clone

When you want to use a remote repo for the first time, you need to clone it first using the below command. For example, to clone a GitHub project:

```console
cd <path where you would like the clone to create a directory>
git clone https://github.com/username/projectname.git
```

We've cloned our previously created repository for the first time.

```console
[$] ~/Desktop
$ git clone https://github.com/sydasif/git-tutorial.git
Cloning into 'git-tutorial'...
remote: Enumerating objects: 6, done.
remote: Counting objects: 100% (6/6), done.
remote: Compressing objects: 100% (4/4), done.
remote: Total 6 (delta 0), reused 6 (delta 0), pack-reused 0
Receiving objects: 100% (6/6), done.
```

This creates a directory called `git-tutorial` on the local machine, containing all the files in the remote Git repository. This includes source files for the project, as well as a `.git` sub-directory which contains the entire history and configuration for the project.

```console
[$] <> ~/Desktop/git-tutorial (main)
$ ls -a
./  ../  .git/  part_01.md  part_02.md  script.py
```

```{Note}
1. When cloning to a specified directory, the directory must be empty or non-existent.
2. You can also use the `ssh` version of the command:

`git clone git@github.com:username/projectname.git`

The `https` version and the `ssh` version are equivalent. However, some hosting services such as GitHub recommend that you use https rather than ssh.
```

## git fetch

The below "git fetch" command retrieves the latest meta-data from the remote repo and updates the same in the local repo.

`git fetch origin`

It doesn’t do any file transferring. It just checks if there are any changes available or not.

```{Note}
In the current case it's optional to do git fetch because git clone will automatically update all metadata. But for later usage fetch will be very useful.
```

## git checkout

It helps to create a branch, a branch is your own copy of the remote repo where you will apply your changes and later push your changes to the remote repository.

`git checkout -b <branch-name>`

In our Eg:

```console
[$] <> ~/Desktop/git-tutorial (main)
$ git checkout -b first-branch
Switched to a new branch 'first-branch'

[$] <> ~/Desktop/git-tutorial (first-branch)
$
```

## git diff

We can check the changes made by us, using the below command:

`git diff <file-name>`

We've modified `script.py` in the new branch. Newly added lines will be shown with the `"+"` prefix and removed lines will be shown with the `"-"` prefix.

```console
[$] <> ~/Desktop/git-tutorial (first-branch)
$ git diff
warning: in the working copy of 'script.py', LF will be replaced by CRLF the next time Git touches it
diff --git a/script.py b/script.py
index e69de29..7df869a 100644
--- a/script.py
+++ b/script.py
@@ -0,0 +1 @@
+print("Hello, World!")
```

Now, using the following sequence of commands we can send our modified file to the remote repo:

```console
[$] <> ~/Desktop/git-tutorial (first-branch)
$ git add script.py 
warning: in the working copy of 'script.py', LF will be replaced by CRLF the next time Git touches it
```

```console
[$] <> ~/Desktop/git-tutorial (first-branch)
$ git commit -m "add code"
[first-branch 8245dcc] add code
 1 file changed, 1 insertion(+)
```

```console
[$] <> ~/Desktop/git-tutorial (first-branch)
$ git push origin first-branch
Enumerating objects: 5, done.
Counting objects: 100% (5/5), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 295 bytes | 295.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: 
remote: Create a pull request for 'first-branch' on GitHub by visiting:
remote:      https://github.com/sydasif/git-tutorial/pull/new/first-branch
remote:
To https://github.com/sydasif/my-repo.git
 * [new branch]      first-branch -> first-branch
```

After this, our code will be added to the respective remote branch.

## git pull

Many times you are working on the same file on which someone else is also working. 

In such a case, before pushing our copy we need to get the latest copy of the same file. Add our changes to it and then push, to avoid any conflicts.

```console
[$] <> ~/Desktop/git-tutorial (first-branch)
$ git pull origin first-branch
From https://github.com/sydasif/my-repo
 * branch            first-branch -> FETCH_HEAD
Already up to date.
```

## Pull Request

In such a case, you need to raise a PR, go through the code review process and then merge your changes on the destination branch.

```{seealso}
- To Create PR: [Creating a pull request](https://docs.github.com/en/enterprise-cloud@latest/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-a-pull-request)
- After Review Merge PR: [Merging a pull request](https://docs.github.com/en/enterprise-cloud@latest/pull-requests/collaborating-with-pull-requests/incorporating-changes-from-a-pull-request/merging-a-pull-request)
```

Congratulations your changes are now in destination branch!
