# GIT & GITLAB TRAINING
This guide is in progress (so we will appreciate any feedback).
It will be used to explain basics of Git and Gitlab.

## Contents

**[Git](#git)**
* [What is Version/source Control ?](#what-is-version-source-control)
* [What is Git ?](#what-is-git)

    **[Git Terminology](#git-terminology)**

    **[Git commands & Local repository](#git-commands-local-repository)**

  * [Initiate a local git repository](#initiate-a-local-git-repository)
  * [Workspaces - Staging - Local - Remote](#Workspaces-staging-local-remote)
  * [Basic commands & usage](#basic-commands-&-usage)
  * [More commands](#more-commands)

**[Remote repositroy - Gitlab](#remote-repository-gitlab)**
* [Remote repository](#remote-repository)
  * [Demo](#demo)
* [comaparing, Branching & Merging](#branching-comaparing-merging)

## Development
**[Git](#git)**
* [What is Version Control ?](#what-is-version-control)

A version control is a way to historize your code modification progressively.

An illustration below
![Collaborative development tracking history](/pics/Hisstory-tracking-2.png)

There are 02 types of Version Control:

- Centralized
- Decentralized / Distributed

Foollowing are the main features of VC
- Versioning / History
- Backup / archive
- Collaboration / Teamwork
- Undo changes
- Isolation of changes
- Comparing
- Code Review

* [What is Git ?](#what-is-git)

Git is an implementation of Decentralized/Distributed Version Control. 

* [Git Terminology](#git-terminology)
- `Working Directory / Workspace`: a directory or folder on your computer that holds all your project/application files. That directory contains `.git/` folder.
- `Staging Area`: A holding area for queuing up changes for the next commit.
- `Repository`: Collection of version controlled files are kept together in *repository*. A place where git stores files and folders of your project.

Have a look on an illustration below

Local Git Workflow

![Local Git Workflow](/pics/local-git-workflow.png)


  **[Git commands & Local repository](#git-commands-local-repository)**
  * [Initiate a local git repository](#initiate-a-local-git-repository)
  * [Workspaces - Staging - Local - Remote](#Workspaces-staging-local-remote)
  * [Basic commands & usage](#basic-commands-&-usage)
      * `git init:` It is used to initialize a *local repository*.
      * `git add: ` Used to add changes to the *staging area*
      * `git status: ` To show the sataus of our current branch. It will print out modified files, files in *staging area* and files that are not tracked.
      * `git diff: ` To print out difference between 02 branches OR between file state in each virtual directories (`*workspace - staging area - local repository*`)
      * `git commit: ` This command adds staging files to your *local repository* 
      * `git push: ` This command adds staging files that have benn commited to the *remote repository*
      * `git branch: ` To list your local branches. You can further manage branches by adding options to that command.
      * `git log: ` To print out the history of all branches and their commits.

  * [More commands](#more-commands)
      * `git ignore`
      * `git stash`
      * `git blame`
      * `git rebase`
      * `git squash`
      * `git revert`
      * `git reset`

**[Remote repositroy - Gitlab](#remote-repository-gitlab)**

A remote repository is repository centrally hosted repo used by a project team for sharing data.

The two following pictures illuatrate the workflow *local repo* (that can be individually hosted by each team member) and *remote repo* (centrally hosted and accessible by all team members)

The first one explains with the associated git command, how files moves from *local workspace* to the *remote repo*. 


Git Workflow - From Local to remote

![Git Workflow - From Local to remote](/pics/git-workflow.png)


The second one explains with the associated git command, members of the same project can commonly use the the *remote repo*.


Team collaboration -  Workflow

![Team collaboration -  Workflow](/pics/team-remote-workflow.png)

  * [Demo](#demo)
    **[create a project called `demo`](#create-a-project-called-demo)**

Before starting, move `*change directory*` to the parent directory that will host your project directory.

      * `git init demo`

Your demo project is now initialised locally. Move to your project derectory.
      * `cd demo`

    **[add remote repo to `demo`](#create-a-project-called-demo)**
As you initialized you rrepo locally, you need to indicate where you remote repos will be hosted.

      * `git remote add origin http://scm.ul.mediametrie.fr/devops/demo.git`

    **[add the first file to repo `demo`](#first-file-to-demo)**
Use any command from your choice to create a file README.md, Then check the status of your workspace.

      * `touch README.md`
      * `git status`

Your repo status currently idicates the following:

- The branch on wich you are *default on master*
- The *untracked* file `README.md` in your workspace
- And that you have nothing in the *staging area*

    **[add text to README.md](#add-text-to-readme.md)**
Use any text editor from your choice to add text to README.md, Then check the status of your workspace.

      * `vim README.md`

Add `# Trainig Git` as first line in `READMEmd` then add the file to the *staging area*

Check your repo status again and try understanding the result.

Add `## Introduction` as second line in `READMEmd` and check your repo status again and try understanding the result once more. Your repo status will idicate the following:

- The branch on wich you are *default on master*
- The new file `README.md` is now in the staging with the *first line* you added before.
- And that you have *new changes - the second line* not yet staged.

      * `git status`

    **[Commit and push](#commit-push)**

Use `commit` and `push` to add chnages locally and remotely.

- Add your last change to the staging area
- `Commit` your chnages to the *local repository*
      * `git commit`
- Check what you just commited with `git log`
      * `git log -u`
- Finally `push` your changes to the remote repos (on *default branch*), to share your local work with your colleagues or project team.
      * `git push origin master`

    **[Ongoing changes - diff](#ongoing-chnages-diff)**

Use any text editor from your choice to add text to README.md, Then check the differencein your workspace.

- Add your demo project description
- Add the introduction description
- Use `git add` to check the difference between the content before and now

      * `git diff`

- Add the changes to the staging area the commit it to te local repos
- You can now check your loacl repos log history to see what changes you made at each commit

      * `git log -u`

- You can now push changes to the remote repos

* [Comaparing, Branching & Merging](#branching-comaparing-merging)

## `Comparing`

    **[Working Directory vs Staging Area](#working-directory-staging-area)**

- Add *Use this demo for guide new user to git and gitlab* to the `Purpose Section` then add the change to the `staging area`

- Add *This is the deployment section for our demo `demo project`* to the `Deployment Section` and simply save the file

- Use `git status` to confirm that your README.md file is in different states (`staged` and `not staged`)

- Use `git diff` to print out the difference: You will only see the last change made. That chnage is in your `working directory` but NOT STAGED YET.

- You can use `git difftool` to visualy show the difference as follow

![Working Directory vs Staging Area (HEAD)](/pics/demo-workspace-vs-staging.png)


    **[Working Directory vs Local Repos](#working-directory-local-repos)**

- Use `git status` to confirm that your README.md file is in different states (`staged` and `not staged`)

- Use `git diff HEAD` to print out the difference between the last commit and your current file status

- You can use `git difftool HEAD` to visualy show the difference as follow

![Working Directory vs Local Repos](/pics/demo-workspace-vs-local-repos.png)


    **[Staging Area vs Local Repos](#staging-area-local-repos)**

- Use `git status` to confirm that your README.md file is in different states (`staged` and `not staged`)

- Use `git diff --staged HEAD` to print out the difference between the local repos and your file status in the staging area

- You can use `git difftool --staged HEAD` to visualy show the difference as follow

![Staging vs Local Repos](/pics/demo-staging-vs-local-repos.png)


    **[Local master vs remote master branch](#local-master-vs-remote-master-branch)**

- Use `git status` to confirm that your README.md file is in different states (`staged` and `not staged`)

- Use `git diff master origin/master` to print out the difference between the local master branch and your file status in the remote repos master branch

## Branching

Before starting branching, commit and push your last cganges to the remote repos.

Branch is a parralel version of your project. The default branch *master* is created when you first initialize your project.

- Check your current branch: `git branch`. This will ouput a list of your branches with the star on the current branch.

### Current branch

Our *demo* project is currently on a single branch called *master* as follow

![Default branch](/pics/demo-branching-default.png)

### Create new branch *feature_0*

To create a new branch, make sure:
- Your are on the parent / source branch
- That you source branch is up to date

Then, use the following command to create the new branch called *feature_0*

      * `git branch feature_0`

You can then check your new branch have been created correctly by listing all branches

      * `git branch -a`

You can now switch to the new branch then and print out your current branch once more to make sure you switched

      * `git checkout feature_0`
      * `git branch`

You can create and switch to the new branch in a single command

      * `git checkout -b feature_0`

![New branch *feature_0*](/pics/demo-branching.png)

When you just created a new branch, the source and the new branch point to the same commit.

From the new branch, run the following command to print out the the state of your pointer

      * `git log --oneline --decorate`

![Pointer Decorate](/pics/demo-branch-decorate.png)

### Commit on new branch *feature_0* and Merge

Add new section to the readme called *Demo feature 0* then add and commit to the branch `feature_0`

#### First commit on new branch

On branch `feature_0`, print out the commit history

      * `git log --oneline --decorate`

The above commands prints out the state of the new branch:

- We remark that the `HEAD` is now pointing only on the new branch
- The commit before is pointing to the master

![First commit on new branch](/pics/first-commit-new-branch.png)

#### Merge `feature_0` to `master` in fast forward way

Switch back to the branch `master`

- Print out the difference between `master` and `feature_0`

      * `git difftool master feature_0`

![Branches diff](/pics/branches-diff.png)

- Now, use `git merge` to merge `feature_0` to `master`

      * `git merge master feature_0`

Git prints out:

- The number of commit identiyig the merge
- Files concerned by merge. In our case it is README.md
- Then the number of `insertions` and `deletions`

Check the state of your pointer once more

      * `git log --oneline --decorate`

You remark that the `HEAD` on `master` moved to the last commit from merged branch.

#### Merge `feature_0` to `master` in no fast forward way

From the branch `master` create the new branche called `feature_1` and switch to that new branch

- Add the new file LICENCE.txt with "2019 Git-Training" and "# Licence" as content then commit
- Add the copyright nitice to README.md then commit

- Print out the log history on `feature_1` then analyse

      * `git log --oneline --decorate --graph`

- Now, use `git merge` to merge `feature_1` to `master`

 First, switch back to the `master` then run the following command

      * `git merge master feature_1 --no-ff`

The below figure explain the `--no-ff` option used

![No Fast Forward Merge](/pics/no-ff-merge.png)

Check the state of your log history and observe

      * `git log --graph --decorate --oneline --all`

![No Fast Forward Merge eg](/pics/no-ff-merge-eg.png)

Git prints out:

- The number of commit identiyig the merge
- A graph presenting each branch wit it own commit
- The branch parent commit
- The merge commit

Delete both feature branches now

      * `git branch -D feature_0 feature_1`


#### Parallel Merge - merge parallel commits from two branches (`parallel-branch` to `master`

From the branch `master` create the new branche called `parallel-branch` and switch to that new branch

- Add the new file teams.txt with "# Teams ## IP ## INFRA ## INFRIP" as content

Switch back on branch `master` and add contribution instructions to the readme then commit

Branch `master` is now in the below state

![Parallel Commit on master](/pics/parallel-commits-master.png)

- Print out the log history on `master` then notice that you have *parralel commits* on both branches now

      * `git log --oneline --graph --decorate --all`

The below figure shows both commits on branches

![Parallel Commit on both branches](/pics/parallel-commits-both-branches.png)


- Now, use `git merge` to merge `parallel-branch` to `master`


      * `git merge master parallel-branch`

The below figure explain the result of that merge

![Parallel Commits Merge](/pics/merge-parralel-commits.png)

![Parallel Commits Merge](/pics/parallel-commits-both-branches-merge.png)


#### Merge Conflicts

From the branch `master` create the new branche called `parallel-branch` and switch to that new branch

- Add the new file teams.txt with "# Teams ## IP ## INFRA ## INFRIP" as content

Switch back on branch `master` and add contribution instructions to the readme then commit

Branch `master` is now in the below state

![Parallel Commit on master](/pics/parallel-commits-master.png)

- Print out the log history on `master` then notice that you have *parralel commits* on both branches now

      * `git log --oneline --graph --decorate --all`

The below figure shows both commits on branches

![Parallel Commit on both branches](/pics/parallel-commits-both-branches.png)


- Now, use `git merge` to merge `parallel-branch` to `master`


      * `git merge master parallel-branch`

The below figure explain the result of that merge

![Parallel Commits Merge](/pics/merge-parralel-commits.png)

![Parallel Commits Merge](/pics/parallel-commits-both-branches-merge.png)



Author Information
------------------

Visquis-MIAFFOSSA @Mediametrie