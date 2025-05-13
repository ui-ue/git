# Introduction to Git and building your first Machine Learning Model

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

## Editing an exisiting file
The best practice when using Git to collaborate on projects is to always run `git pull` before working on your part as you will receive the updated code made by your teammates.

On the main repository page, click on "Fork" option on the top right. It is as follows:

<img width="1728" alt="Screenshot 2025-05-05 at 10 00 07 pm" src="https://github.com/user-attachments/assets/3d5c68ae-b89b-4a68-9452-3d25e96f4c95" />

Click on the option "Create Fork":

<img width="1728" alt="Screenshot 2025-05-05 at 10 02 32 pm" src="https://github.com/user-attachments/assets/772067cf-780a-4cb0-9abd-dac81fb69c2d" />

Now, copy the new forked URL and clone the repository using this URL in directory of your choice. The new URL should have your GitHub username. Run the command `git clone https://github.com/<username>/workshops`.

<img width="1728" alt="Screenshot 2025-05-05 at 10 04 09 pm" src="https://github.com/user-attachments/assets/c93d87bd-b153-4047-b030-3add96943037" />

Navigate into the repository, and type the command `code test.py`. This will open the selected file in VS Code. If you'd like to open the current directory, type the command `code .` or if u want to open both the directory and the file `test.py`, run the command `code . test.py`.

Type in any line of code you like, say for example `print("Hello World!")`. Once you have done this, save the file (ctrl/cmd + s) and switch back to the terminal. Type the command `git status` to see which files have been modified. This is a very useful command which shows the files that have been modified, staged or have gone untracked. 

Now, run the command `git add <file(s)>` or in this instance, `git add test.py`. This command stages the file for the incoming commit.

Now run `git commit -m "message"` or here `git commit -m "edited the file test.py"`. This command records a snapshot of the commit with the change, and also allows you to put in a commit message of your choice.

Finally, run the command `git push`, which commits the change made from the local repo on your machine to its remote counterpart.

## Working with Branches and Pull Requests

In real-world projects, it's best practice to **create branches** when developing new features or fixing bugs. This allows you to make changes in isolation from the `main` branch, which usually contains the production-ready code.

### Creating and Switching to a Branch

To create and switch to a new branch, use:

```bash
git checkout -b <branch-name>
```

For example:

```bash
git checkout -b feature/add-ml-model
```

This command:

* Creates a new branch called `feature/add-ml-model`
* Switches you to that branch immediately

You can check what branch you’re on using:

```bash
git branch
```

The active branch will be highlighted with an asterisk `*`.

### Making Changes on a Branch

Once you're on your new branch, edit files as usual. When you're done:

1. Stage changes: `git add .`
2. Commit them: `git commit -m "feat(ml_model): Implemented basic ML Model"`
3. Push the branch to the remote repo:

   ```bash
   git push -u origin feature/add-ml-model
   ```

### Opening a Pull Request (PR)

Now that your branch is on GitHub:

1. Go to the GitHub repository in your browser.
2. You’ll see a prompt to open a **Pull Request** (PR) for your new branch.
3. Click **“Compare & pull request”**.
4. Fill in the title and description of your changes.
5. Submit the PR.

Pull Requests are how team members review and discuss code before it gets merged into the main codebase.

### Reviewing and Merging a Pull Request

Once the PR is opened:

* Teammates can leave comments, suggest changes, or approve the PR.
* After review, someone (often the author or a maintainer) will merge it using the **“Merge pull request”** button.

Once merged, your branch’s changes become part of the `main` branch.

### Cleaning Up

After a successful merge, you can delete the branch both locally and remotely:

```bash
# Delete the branch locally
git branch -d feature/add-ml-model

# Delete the branch remotely
git push origin --delete feature/add-ml-model
```

---

### Recap: Why Use Branches and PRs?

* **Safety:** Isolate work to avoid breaking the main codebase.
* **Collaboration:** Discuss, review, and improve code together.
* **History:** Keep your git history clean and meaningful.