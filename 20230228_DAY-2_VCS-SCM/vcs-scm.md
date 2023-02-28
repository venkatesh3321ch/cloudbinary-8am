#### Session Video:
    https://s3.amazonaws.com/kesavkummari.aws/8am_AWSDevOps20230207/8am_awsdevops_20230227_2/20230228_DAY-2_VCS-SCM/video1234192092.mp4

# Version Control System / Source Code Management : Git

####
    - Getting Started with VCS//SCM
    - What is Git, AWS CodeCommit and GitHub?
    - About Version Control System and types
    - Git Workflow
    - Installing on Windows & Linux
    - Getting Started with Git Commands
    - Working with Branches
    - Merging Branches
    - Creating and Committing a Pull Request
    - Working with Stash

#### What is a Version Control System?

    - A Version Control System (VCS) is a software tool that helps developers manage changes to their code over time. 
    - VCS allows developers to track and record changes made to a project's source code, enabling collaboration and simplifying the process of resolving conflicts between different versions of the same code.

#### Why do we need a Version Control System?

    VCS has become essential in software development for the following reasons:
        - Collaboration: VCS allows multiple developers to work on the same codebase simultaneously, without risking conflicts or losing important code changes.

        - History Tracking: VCS provides a detailed history of all changes made to the code, including who made the changes, when the changes were made, and why they were made.

        - Code Backup: VCS provides a backup of the code at any given point in time, enabling developers to restore a previous version if necessary.

        - Rollback: VCS provides the ability to revert changes, undoing the effects of previous code changes.

#### Types of Version Control Systems

    There are two types of VCS:
    
    1. Centralized Version Control System (CVCS) 
        - In CVCS, there is a central server that stores all code changes made by developers. 
        - Developers checkout code from the server and make changes to their local copies. 
        - After making changes, developers commit the changes to the central server. 
        - Examples of CVCS include Subversion (SVN) and Perforce.

    2. Distributed Version Control System (DVCS)
        - In DVCS, each developer has a local copy of the code, and code changes are synchronized between the local copies. 
        - Each developer can commit code changes to their local copy and push those changes to other developers. 
        - Examples of DVCS include Git and Mercurial.

#### Git Workflows

    1. Centralized Workflow
        In a centralized workflow, there is a single central repository that serves as the "source of truth." Developers clone the repository, make changes locally, and push their changes to the central repository. This workflow is simple and easy to understand, but it can lead to conflicts if multiple developers are working on the same code at the same time.

    2. Feature Branch Workflow
        In a feature branch workflow, each feature or change is developed in a separate branch. Developers clone the repository, create a new branch for their feature, make changes, and submit a pull request to merge their changes back into the main branch. This workflow allows for better collaboration and reduces the risk of conflicts.

    3. Gitflow Workflow
        Gitflow is a branching model that uses two main branches: a master branch for stable releases and a develop branch for ongoing development. Developers create feature branches off the develop branch, make changes, and submit pull requests to merge their changes back into the develop branch. Once the develop branch is stable, it is merged into the master branch for a release. This workflow is well-suited for larger teams working on long-term projects with frequent releases.

    4. Forking Workflow
        In a forking workflow, each developer forks the main repository into their own repository, makes changes in their fork, and submits a pull request to merge their changes back into the main repository. This workflow is useful for open-source projects, as it allows contributors to make changes without needing write access to the main repository.

    Note: These are just a few examples of Git workflows. The specific workflow used may vary depending on the team's needs and preferences. It's important to choose a workflow that fits the team's development process and supports collaboration and communication.
       
#### We'll focus on Git, which is the most widely used DVCS.
    To get started with Git, follow these steps:
        - Install Git
        - The first step is to install Git on your machine. 
        - You can download Git from the official website (https://git-scm.com/downloads).

        Create a Git repository:
            - After installing Git, you can create a new Git repository by running the following command:
            $ git init

        - This command creates a new Git repository in the current directory.

        Add files to the repository:
            - Once you've created a new Git repository, you can add files to it using the following command:
            $ git add <filename>

        This command stages the file for commit. You can stage multiple files at once by specifying their filenames separated by spaces.

        Commit changes:
            - After adding files to the repository, you can commit changes using the following command:
            $ git commit -m "commit message"

            This command commits the changes to the repository along with a descriptive commit message. The commit message should explain the changes made to the code.
        View repository history:
            - You can view the history of the Git repository using the following command:
            $ git log

            This command displays a list of all commits made to the repository, including the commit hash, commit message, and author.
        
        Branching:
            - One of the key features of Git is branching. 
            - A branch is a separate line of development that allows developers to work on new features or bug fixes without affecting the main codebase. 

            To create a new branch, run the following command:
                $ git branch <branchname>

            This command creates a new branch with the specified name. 
            
            To switch to the new branch, run the following command:
                $ git checkout <branchname>

#### Here is a list of some common Git commands:

    git init: Initializes a new Git repository in the current directory.

    git clone: Clones an existing Git repository from a remote location to your local machine.

    git add: Adds changes to the staging area.

    git commit: Commits changes to the repository.

    git status: Shows the status of the working directory and staging area.

    git log: Shows the commit history.

    git branch: Lists all branches in the repository.

    git checkout: Switches to a different branch or commit.

    git merge: Merges changes from one branch into another.

    git pull: Fetches changes from a remote repository and merges them into the local branch.

    git push: Sends changes from the local branch to a remote repository.

    git stash: Saves changes temporarily without committing them.

    git tag: Creates a new tag for a specific commit.

    git remote: Shows the remote repositories linked to the local repository.

    git fetch: Fetches changes from a remote repository without merging them into the local branch.

#### Here are some Git commands with examples:

    ```
    git init: Initializes a new Git repository in the current directory.
    
    $ git init
    Initialized empty Git repository in /path/to/repository
    git clone: Clones an existing Git repository from a remote location to your local machine.
    ```

```
$ git clone https://github.com/user/repository.git
Cloning into 'repository'...
remote: Counting objects: 100, done.
remote: Compressing objects: 100% (80/80), done.
remote: Total 100 (delta 20), reused 100 (delta 20), pack-reused 0
Receiving objects: 100% (100/100), done.
Resolving deltas: 100% (20/20), done.
git add: Adds changes to the staging area.
```

```
$ git add file.txt
git commit: Commits changes to the repository.

```

```
$ git commit -m "Commit message"
[main 12a34b5] Commit message
 1 file changed, 1 insertion(+)
git status: Shows the status of the working directory and staging area.
```

```
$ git status
On branch main
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
        modified:   file.txt
git log: Shows the commit history.
```

```
$ git log
commit 12a34b5d6e7f8a9b0c1d2e3f4a5b6c7d8e9f0g1h (HEAD -> main)
Author: John Doe <john.doe@example.com>
Date:   Mon Feb 21 10:00:00 2022 -0500

    Commit message
git branch: Lists all branches in the repository.
```

```
$ git branch
  main
* feature-branch
git checkout: Switches to a different branch or commit.
```

```
$ git checkout main
Switched to branch 'main'
git merge: Merges changes from one branch into another.
```

```
$ git merge feature-branch
Merge made by the 'recursive' strategy.
  file.txt | 2 ++
  1 file changed, 2 insertions(+)
git pull: Fetches changes from a remote repository and merges them into the local branch.
```

```
$ git pull origin main
From https://github.com/user/repository
 * branch            main       -> FETCH_HEAD
Updating 12a34b5d6e7f..23b45c6d7e8f
Fast-forward
 file.txt | 1 +
 1 file changed, 1 insertion(+)
git push: Sends changes from the local branch to a remote repository.
```

```
$ git push origin main
Counting objects: 4, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (2/2), done.
Writing objects: 100% (4/4), 358 bytes | 358.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
```

#### Git Rebase
    - Git rebase is a Git command used to apply changes from one branch to another by reapplying each commit on top of the destination branch. 
    
    - It allows for a cleaner and more linear commit history than traditional merge workflows.

    The basic syntax of git rebase is as follows:
    ```
    $ git checkout <source-branch>
    $ git rebase <destination-branch>
    Here, <source-branch> is the branch that you want to apply the changes from, and <destination-branch> is the branch that you want to apply the changes to.
    ```

    For example, let's say you have the following commit history on a branch called feature-branch:
    ```
    A - B - C (feature-branch)
         \
          D - E (main)
    ```

    You want to apply the changes from feature-branch to main and make the commit history look like this:
    
    ```
        A - B - C - D' - E' (main)
        
    To do this, you would run the following commands:
    
    ```
    $ git checkout feature-branch
    $ git rebase main
    
    ```

    This would rebase the changes in feature-branch on top of main, resulting in a new commit history where the changes from feature-branch are applied on top of the latest changes in main.

    It's important to note that git rebase rewrites the commit history of the branch being rebased. This means that it can cause conflicts if other developers have pulled and worked on the same branch. It's generally recommended to use git rebase on feature branches that are not shared with other developers.

#### git merge vs git rebase

    git merge and git rebase are two different Git commands used to integrate changes from one branch to another. While both commands achieve the same result, they do it in different ways and have different use cases.

    git merge is a command used to integrate changes from one branch into another. It creates a new commit that combines the changes from both branches. This new commit has two parent commits, one from each branch. This creates a merge commit, which shows up in the commit history.

    ```
        $ git checkout destination-branch
        $ git merge source-branch

    ```
    git rebase is a command used to integrate changes from one branch into another by reapplying each commit on top of the destination branch. It essentially moves the entire source branch to the tip of the destination branch, creating a linear commit history. This avoids the creation of a merge commit.

    ```
        $ git checkout source-branch
        $ git rebase destination-branch

    ```

#### Here are some key differences between git merge and git rebase:

    git merge creates a new merge commit, while git rebase rewrites the commit history.

    git merge maintains a separate branch history, while git rebase results in a linear commit history.

    git merge preserves the original commit history of both branches, while git rebase discards the original commit history of the source branch.

    git merge is recommended for merging changes from shared branches, while git rebase is recommended for feature branches that are not shared with other developers.

#### git stash

    git stash is a command used to temporarily save changes in a working directory, without committing them. This can be useful if you need to switch branches or work on something else, but you don't want to commit incomplete changes. Here are some examples of how to use git stash:

    Stash changes:

    $ git stash save "WIP: work in progress"

    This command saves any changes in the working directory to a new stash. The message "WIP: work in progress" is an optional description of the stash.

    List stashes:

    $ git stash list
    
    This command lists all stashes that have been saved.

    Apply a stash:

    $ git stash apply stash@{0}
    
    This command applies the changes from the stash at index 0. The changes are not removed from the stash.

    Apply a stash and remove it:

    $ git stash pop stash@{0}
    
    This command applies the changes from the stash at index 0 and removes it from the stash list.

    Apply a specific file from a stash:

    $ git stash apply stash@{0} -- <file>
    
    This command applies the changes from the specified file in the stash at index 0.

    Create a branch from a stash:

    $ git stash branch new-branch stash@{0}
    
    This command creates a new branch called "new-branch" and applies the changes from the stash at index 0 to the new branch.

    These are just a few examples of how git stash can be used. It's a powerful command that can be used to save changes temporarily and apply them later.

#### Git Use cases
    Git is a powerful tool for version control and has many use cases. Here are some examples of how Git can be used:

    1. Software Development:
        Git is widely used in software development to manage source code. Developers use Git to track changes to their codebase, collaborate with other developers, and manage different versions of the code. By using branching and merging features, developers can work on different features or bug fixes simultaneously without impacting the main codebase. Git also provides a complete history of all changes made to the codebase, making it easier to revert to a previous version if needed.

    2. Collaboration:
        Git is also used for collaboration, especially in remote or distributed teams. By using Git, team members can work on the same codebase simultaneously, share code changes, and track progress. Git also enables teams to review code changes, provide feedback, and discuss solutions, all within the Git platform. This enhances collaboration and ensures that everyone is working towards the same goals.

    3. Continuous Integration and Deployment:
        Git can also be used in conjunction with Continuous Integration (CI) and Continuous Deployment (CD) tools. By integrating Git with these tools, developers can automate the process of building, testing, and deploying their code changes. Git hooks can be used to trigger automated builds and tests whenever changes are made to the codebase. This ensures that code changes are thoroughly tested and deployed quickly, without manual intervention.

    4. Documentation Management:
        Git can also be used for managing documentation, such as software documentation or technical manuals. By using Git, developers can track changes made to the documentation, collaborate with other writers, and maintain multiple versions of the documentation. Git also provides a complete history of all changes made to the documentation, making it easier to track changes and revert to a previous version if needed.

    5. Personal Projects:
        Finally, Git can also be used for personal projects, such as managing your own codebase or tracking changes to a personal project. By using Git, you can maintain a complete history of all changes made to your codebase, revert to a previous version if needed, and collaborate with others if you choose to do so. Even if you are not working in a team, Git can still be a valuable tool for managing your code and tracking changes over time.
