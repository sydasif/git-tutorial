# 1. Git and GitHub

Git is a distributed version control system (VCS) that maintains a history of changes to files for reference and rolls back a change. It is a software for tracking changes in any set of files, usually used for coordinating work among programmers who are collaborating on the same source code, and widely used, released under GNU GPL v2 license.

It's decentralized in nature, helping the larger team to work together. Every developer has their own copy of the repository on their machine, they can locally work without the internet on their machine and commit their changes.

Once their work is done they can publish their changes on a remote git repository and share them with other developers.

Git can:

- track changes in file
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

## Setting-Up Git

After Download Git from the website, using the command line is better for cross-platform transformation because command lines are the same for Mac-OS, Linux, and Windows.

### Configuration of Git

To start working with Git you need to specify the `user.name` and `user.email`. This is important because every Git commit uses this information and that will be used to synchronize the local repository with your GitHub repository:

```shell
[$] git config --global user.the name "John Woe"
[$] git config --global user.email "johnwoe@example.com"
```

If you want to use a different text editor, such as Vim, you can do the following:

```shell
[$] git config --global core.editor "vim"
```

By default, Git will create a branch called master when you create a new repository with git init. From Git version 2.28 onwards, you can set a different name for the initial branch.

To set main as the default branch name do:

```shell
[$] git config --global init.defaultBranch main
```

If you want to check your configuration settings, you can use the git config --list command to list all the settings:

```shell
[$] git config --list
user.name=John Woe
user.email=johnwoe@example.com
core.editor=vim
init.defaultbranch=main
```

All these git settings are stored in the .gitconfig file in the user's home directory. Now you can edit using git config --global --edit will open the ~/.gitconfig file in a text editor as below:

```shell
  [user]                                                                      
      name = John Woe
      email = johnwoe@example.com
  [core]
      editor = vim
  [init]
      defaultBranch = main
```

We can also configure git, creating a .gitconfig file in under the user's home directory and pasting the above settings.
