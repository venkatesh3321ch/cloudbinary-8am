#### Session Video
    - https://s3.amazonaws.com/kesavkummari.aws/8am_AWSDevOps20230207/8am_awsdevops_20230227_2/20230227_DAY-1_VCS-SCM/video1928300959.mp4

# Agenda 
    - VCS / SCM

#### Version Control System / Source Code Management : Git
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

#### Git Workflow
1. Centralized Workflow
    In a centralized workflow, there is a single central repository that serves as the "source of truth." Developers clone the repository, make changes locally, and push their changes to the central repository. This workflow is simple and easy to understand, but it can lead to conflicts if multiple developers are working on the same code at the same time.

2. Feature Branch Workflow
    In a feature branch workflow, each feature or change is developed in a separate branch. Developers clone the repository, create a new branch for their feature, make changes, and submit a pull request to merge their changes back into the main branch. This workflow allows for better collaboration and reduces the risk of conflicts.

3. Gitflow Workflow
    Gitflow is a branching model that uses two main branches: a master branch for stable releases and a develop branch for ongoing development. Developers create feature branches off the develop branch, make changes, and submit pull requests to merge their changes back into the develop branch. Once the develop branch is stable, it is merged into the master branch for a release. This workflow is well-suited for larger teams working on long-term projects with frequent releases.

4. Forking Workflow
    In a forking workflow, each developer forks the main repository into their own repository, makes changes in their fork, and submits a pull request to merge their changes back into the main repository. This workflow is useful for open-source projects, as it allows contributors to make changes without needing write access to the main repository.

Note: These are just a few examples of Git workflows. The specific workflow used may vary depending on the team's needs and preferences. It's important to choose a workflow that fits the team's development process and supports collaboration and communication.

#### Download, Install & Configure Git, & Visual Studio on Windows :
    https://s3.amazonaws.com/kesavkummari.aws/10am_AWSDevOps_DAY-1_20230223/video1841516763.mp4

- Download, Install & Configure VSC/SCM CLI Tool i.e. Git on Host Machine
    - https://git-scm.com/
        

- Download, Install & Configure IDE(integrated development environment) Tool on Host Machine
    - https://visualstudio.microsoft.com/


#### Q?
    - 

