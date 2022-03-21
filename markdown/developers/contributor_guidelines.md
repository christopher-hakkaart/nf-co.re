---
title: Contributing to an existing nf-core pipeline
subtitle: How to make a contribution to an existing pipeline
--- 

## Before you start

One of the fundimental nf-core concepts is to work together to create best practise workflows through colaboartion rather than duplication.
Nf-core achieves this by being an open and inclusive community that welcomes contributions.
In many cases, the current developers may not be aware of a bug you would like to fix, have experience with the method, tool, or feature you want to implement, or simply don't have time to implement an idea themselves.
You may be the missing piece of the puzzle!

If you are new to nf-core and nextflow, here are some great resources that will help you get started:
- [An introduction to nf-core and nextflow](https://nf-co.re/usage/introduction)
- [Nf-core pipeline guidelines](https://nf-co.re/developers/guidelines)
- [Working with git and GitHub](https://blog.scottlowe.org/2015/01/27/using-fork-branch-git-workflow/)

## Basic rules for contributions

Contributions to an exisitng pipeline follow the same rules and patterns as [adding a new pipeline](https://nf-co.re/developers/adding_pipelines). However, to make sure everyone has an opportunity to contribute there is a simple process to follow:
1. Ask in the Slack channel for the specific pipeline whether there is an open GitHub issue on the respective pipeline's issue tracker for the feature you're planning to add, fix, or develop.
2. If no GitHub issue exists, create a new issue describing the purpose and the ideas you have, and wait for someone to comment/discuss the issue.
3. If everyone is happy or there is some consensus in the community, start implementing the feature in your fork of the respective pipeline (see below).

To keep the process as simple as possible, please do not write to multiple channels in the Slack community, rather collect all of the information for your proposal in a single issue.

As all nf-core pipelines use GitHub as their code repository, and git as their version control, making a contribution to any nf-core pipeline will generally follow the same pattern:
1. [Fork](#fork)
2. [Clone](#clone)
3. [Branch](#branch)
4. [Edit](#edit)
5. [Commit](#commit)
6. [Push](#push)
7. [Create a pull request](#create-a-pull-request)

### Fork

On GitHub.com navigate to the repository you want to contribute towards.
Click on the `Fork` button (located in the top right corner the git repository) to copy the nf-core pipeline repository into your own Github repository.

### Clone

On your command line, navitage to a directory you want to work from and use `git clone` to make a local copy of **your** forked version of the pipeline repository.

```bash
git clone https://github.com/<your-profile>/<repository-name>.git
```

While the master branch contains the code from the latest stable release, you will most likely want to make your new branch from the `dev` branch that will contain the latest development code.
By default `git clone` will make a clone of the default branch of the repository.
Cloning a specific branch is achieved by using `-branch` with the name of the branch you want to use as your starting point.
For example, if you wanted to clone the `dev` branch of the pipeline, your command would be:

```bash
git clone -branch <dev> https://github.com/<your-profile>/<repository-name>.git
```

### Branch

It is reccommened you make a new branch to work on. To make it easier to keep track of it's best to name it something that reflects what you are working on.

```bash
git checkout -b <myFeature> <dev>
```

### Edit

Make your changes to the pipeline.
Nf-core has a set of coding conventions and linting tests to keep everything consistent and readable.

[code editors](https://nf-co.re/developers/editor_plugins)
[syn](https://nf-co.re/developers/sync)

### Commit

Add and commit your changes locally.
Remeber to write a message that reflects the changes you have made.

```bash
git add .
git commit -m "Added new feature myFeature"
```

### Push

The first time you push your local commit to your remote repository you will need to set a remote as upstream.

```bash
git push --set-upstream origin <myFeature>
```

Any subsequent changes can be pushed using a standard `push` command.

```bash
git push
```

### Create a pull request

When you are happy with your changes and they are passing checks you can create a pull request between your remote branch and the nf-core pipeline repository.
Pull requests to the nf-core fork have a number of automated steps that must pass before the PR can be merged. A few points to remember are:
- The pipeline CHANGELOG.md must be updated
- Pull requests must not be against the master branch
- Pull requests need to be reviewed by someone else before being merged (you can ask for help on the #request-review Slack channel if needed)

## Other for now


