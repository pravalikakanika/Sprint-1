# Proof of Concept: VCS Branching Strategy Using Git Flow

![image](https://github.com/user-attachments/assets/d47c41b9-e240-4233-ba02-a391999d6568)


| Author        | Date       | Version | Review Level   | Reviewer Name        |
|---------------|------------|---------|----------------|----------------------|
| pravalika Kanikarapu  |    | v1.0    | Pre-Reviewer   | Priyanshu            |
| pravalika Kanikarapu  |    |     | L0             | priyanka      |
| pravalika Kanikarapu  |            |         | L1             | Rishabh Sharma       |
| pravalika Kanikarapu  |            |         | L2             | piyush Upadhyay      |


# Table of Contents

- [Introduction](#introduction)
- [What is Git Flow](#what-is-git-flow)
- [Why Git Flow?](#why-git-flow)
- [Workflow Diagram](#workflow-diagram)
- [Advantages of Git Flow](#advantages-of-git-flow)
- [Disadvantages of Git Flow](#disadvantages-of-git-flow)
- [Conclusion](#conclusion)
- [Contact Information](#contact-information)
- [References](#references)







# Introduction

This document outlines the purpose and structure of the Git Flow branching strategy to help teams manage code effectively.
It details the workflow, including the roles of feature, develop, release, and hotfix branches, promoting organized and parallel development. The advantages and limitations of Git Flow are also discussed to guide teams in deciding when and how to adopt it.


# What is Git Flow ?

Git Flow is a branching model for Git, created by Vincent Driessen, that defines a strict branching strategy designed around the project release cycle. It provides a robust framework for managing larger software projects and collaborative development, bringing clarity and consistency to your workflow.
Git Flow supplements the existing Git commands with extensions that simplify working with feature branches, release branches, hotfixes, and more.


# Why Git Flow?



In growing teams and complex projects, handling releases, bug fixes, and new features can get chaotic. Git Flow offers a clear branching model that supports:

- **Parallel development** via feature branches.
- **Timely releases** through dedicated release branches.
- **Quick emergency fixes** with hotfix branches.
- A **stable main branch** at all times.

This model works especially well for projects with scheduled release cycles and multiple environments (e.g., development, staging, production).

# Workflow Diagram

![image](https://github.com/user-attachments/assets/ff248010-47dd-4714-acc6-3b2dee97b968)

## Working Directory
The **Working Directory** is where you actively work on your project files. These files may or may not be tracked by Git. Any untracked files are considered "local" and are not under Git's control until you explicitly tell Git to track them. Changes made in the working directory are not saved to Git until you commit them.

- **Untracked files**: Files that Git isn't aware of yet.
- **Tracked files**: Files that Git is tracking for changes.

If you make changes to files in the working directory without saving them to Git, you will lose those changes as Git is not monitoring them.

## Staging Area
The **Staging Area** (also known as the **Index**) is where you prepare changes before committing them to the local repository. When you run `git add`, you move files from the Working Directory to the Staging Area. 

- Changes are saved in the `.git` directory.
- Git only tracks the changes that are added to the Staging Area. If you modify a file in the Staging Area, Git will not track the changes until you explicitly stage it again using `git add`.

## Local Repository
The **Local Repository** is the storage area where your project's commits are saved. When you use `git commit`, the changes in the Staging Area are saved into the Local Repository (the `.git` directory). After a commit, the Staging Area is cleared, and the changes are now part of the project’s history.

- **View commit history**: You can use `git log` to see the commits stored in the Local Repository.
- Changes in the Local Repository are local to your environment. To share them with others, you'll need to push the changes to a remote repository.

## Remote Repository
The **Remote Repository** is where your project is stored online or on a network server. It allows multiple developers to collaborate by pushing and pulling changes to and from a central location. Common services for remote repositories include GitHub, GitLab, and Bitbucket.

- **Push**: To upload your local commits to the remote repository, you use the command `git push`. This allows others to see and use your changes.
- **Pull**: To fetch and merge changes from the remote repository to your local repository, you use the command `git pull`. This keeps your local repository up-to-date with the latest changes from other contributors.
- **Clone**: You can create a local copy of a remote repository by using `git clone`, which allows you to start working on a project that is stored remotely.


##  Advantages and  Disadvantages of Git Flow

| Advantages                         | Disadvantages                          |
|------------------------------------|----------------------------------------|
| **Clear Structure**: Each branch has a specific role, reducing confusion. | **Complexity**: More branches mean more overhead, especially for small teams. |
| **Parallel Development**: Teams can work on features independently. | **Not Ideal for CI/CD**: Slower to adapt to continuous delivery or deployment models. |
| **Stable Releases**: `main` branch always reflects the production state. | **Heavyweight for Simple Apps**: Smaller projects may find it unnecessarily complicated. |
| **Easy Maintenance**: Hotfixes are isolated and quick to deploy. | **Tooling Dependence**: Some flows need tools like the `git-flow` CLI extensions. |
| **Scalable**: Works well with large teams and long-term projects. |  |

# Conclusion

Git Flow is a powerful branching strategy for teams that need a structured approach to software development. While it introduces some complexity, it shines in release-driven environments by promoting code quality and workflow consistency. Teams should evaluate their needs and consider Git Flow if they are managing multiple environments and need robust version control practices.

#  Contact Information


| Name       | Email Address                |
|------------|------------------------------|
| Pravalika  | kanikarapu.pravalika.snaatak@mygurukulam.co|

# References 

| Link | Description |
|------|-------------|
| [Gitflow](https://medium.com/club-infosphere/a-walk-through-to-github-908485f8ecda) | Documentation followed from this guide |






