# Introduction to Git and building your first Maching Learning Model

## What is Git?
**Git** is a distributed version control system that lets you track changes in your code or any text file, collaborate safely with others, and rollback mistakes easily.  Developers typically start by creating—or “initializing”—a repository (the `.git` folder that tracks all changes) on their local machine or by cloning an existing remote repository ("repo" for short) from a service like GitHub, GitLab, or Bitbucket. Once they have a repo, they:
- **Make commits locally:** As they write or modify code, they stage changes with `git add` nd record snapshots with `git commit`.
- **Push to remote repos:** When they’re ready to share work or back it up, they send their commits to a central remote repository using `git push`, making their updates available to teammates.
- **Pull updates:** To incorporate teammates’ changes, they use `git pull` (which fetches new commits from the remote and merges them locally) or run `git fetch` followd by `git merge` or more control.
- **Branch for features:** They create lightweight branchesto develop new features or fixes in isolation and then merge them back into main branches when complete .
- **Collaborate via pull requests:** On platforms like GitHub, they open a pull request to propose merging a branch into the main code line, enabling code review, discussion, and automated testing before integration.
- **Resolve conflicts:**  If two people edit the same lines, Git flags a merge conflict; developers then manually reconcile the differences, commit the resolution, and continue.
- **Tag releases:** They mark specific commits as releases to track versions and roll back if necessary.

## Typical Everyday Workflow
1. **Edit Code**
2. **Stage & Commit** your changes locally
3. **Push** to the teams remote repository
4. **Review** teammates' work via pull requests
5. **Pull** their changes into your local repository
6. **Repeat**

# Getting Started with Git

## Making your first Repository
To make your first Git repository on your machine, open Terminal (Mac) or Powershell (Windows) and navigate to any directory you wish or simply make a new directory using `mkdir <dir_name>` and type the command `git init`. You have now created a Git repository in your directory!

## Cloning a remote repository
To clone a remote repository onto your local machine, you need the URL of the repository. For instance here, lets clone this current repository onto your machine.

Navigate to the directory of your choice on your computer and run the command `git clone <repositoryURL>`, or in this instance, `git clone https://github.com/SUAIA-USYD/workshops`. And there you have it! You have successfully cloned into the repository of this workshop. To check, run the command `cd workshops` and it should take you to the cloned repository. Just run `ls` to view the files in the repo.

## Editing an exisitng file
The best practice when using Git to collaborate on projects is to always run `git pull` before working on your part as you will receive the updated code made by your teammates.

Navigate into the repository, and type the command `code test.py`. This will open the selected file in VS Code. If you'd like to open the current directory, type the command `code .` or if u want to open both the directory and the file `test.py`, run the command `code . test.py`.

Type in any line of code you like, say for example `print(Hello World!)`. Once you have done this, save the file (ctrl/cmd + s) and switch back to the terminal. Type the command `git status` to see which files have been modified. This is a very useful command which shows the files that have been modified, staged or have gone untracked. 

Now, run the command `git add <file(s)>` or in this instance, `git add test.py`. This command stages the file for the incoming commit.

Now run `git commit -m "message"` or here `git commit -m "edited the file test.py"`. This command records a snapshot of the commit with the change, and also allows you to put in a commit message of your choice.

Finally, run the command `git push`, which commits the change made from the local repo on your machine to its remote counterpart.
