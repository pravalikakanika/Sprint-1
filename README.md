
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

This document outlines the purpose, workflow, advantages, and limitations of Git Flow, helping teams adopt a structured Git branching strategy.



# What is Git Flow

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

![git-flow-4](https://github.com/user-attachments/assets/4af1dbf7-ea62-482b-815d-97b9d28039a2)

## Main Branch

In Git flow, the main branch is created at the start of a project and is maintained throughout the development process. The branch can be tagged at various commits in order to signify different versions or releases of the code, and other branches will be merged into the main branch after they have been sufficiently vetted and tested.

## Develop Branch
The develop branch is created at the start of a project and is maintained throughout the development process, and contains pre-production code with newly developed features that are in the process of being tested.

## Feature Branch

The feature branch is the most common type of branch in the Git flow workflow. It is used when adding new features to your code.When working on a new feature, you will start a feature branch off the develop branch, and then merge your changes back into the develop branch when the feature is completed and properly reviewed.

## Release Branch

The release branch should be used when preparing new production releases. Typically, the work being performed on release branches concerns finishing touches and minor bugs specific to releasing new code, with code that should be addressed separately from the main develop branch.

## Hotfix Branch

In Git flow, the hotfix branch is used to quickly address necessary changes in your main branch.The base of the hotfix branch should be your main branch and should be merged back into both the main and develop branches. Merging the changes from your hotfix branch back into the develop branch is critical to ensure the fix persists the next time the main branch is released.

# Advantages of Git Flow

- **Clear structure**: Each branch has a specific role, reducing confusion.
- **Parallel development**: Teams can work on features independently.
- **Stable releases**: Main branch always reflects the production state.
- **Easy maintenance**: Hotfixes are isolated and quick to deploy.
- **Scalable**: Works well with large teams and long-term projects.

# Disadvantages of Git Flow

- **Complexity**: More branches mean more overhead, especially for small teams.
- **Not ideal for CI/CD**: Slower to adapt to continuous delivery or deployment models.
- **Heavyweight for simple apps**: Smaller projects may find it unnecessarily complicated.
- **Tooling dependence**: Some flows need tools like the git-flow CLI extensions.

# Conclusion

Git Flow is a powerful branching strategy for teams that need a structured approach to software development. While it introduces some complexity, it shines in release-driven environments by promoting code quality and workflow consistency. Teams should evaluate their needs and consider Git Flow if they are managing multiple environments and need robust version control practices.

#  Contact Information


| Name       | Email Address                |
|------------|------------------------------|
| Pravalika  | kanikarapu.pravalika.snaatak@mygurukulam.co|

# References 

| Link | Description |
|------|-------------|
| [https://www.gitkraken.com/learn/git/git-flow](https://www.gitkraken.com/learn/git/git-flow) | Documentation followed from this guide |








