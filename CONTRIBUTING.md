# Contributing

* [Definitions](#definitions): **please read this section first**.
* [Branch Policy](#branch-policy): describes the project's branching strategy.
* [Contribution Guidelines](#contribution-guidelines): describes how to send a 
contribution to the project.
* [Additional Documentation](#additional-documentation): some extra stuff that 
may be worth reading before start working on your contribution.

## Definitions

#### Upstream
The main Git repository of the project (this is not the same as the `main` 
branch). It is common to fork a project to send contributions (see [Contribution
Guidelines](#contribution-guidelines) section). Those forks need to be aligned 
with the upstream repository. We usually need the fork because we don't have
write permission to send commits to the original (upstream) repository. The
fork is our own copy of the project and allows us to do whatever we want. Once
our set of changes is ready, we will send a Pull Request to the upstream
repository to get our contribution reviewed for merging. 

#### Clean merge
A merge that is performed on a branch, without any other merges in between. Next
screenshot shows **what IS NOT a clean merge** and therefore we get a dirty Git 
graph. It's difficult to see the scope of each change and rolling back can be a
nightmare:

![Clean and clear merge seen from `git log --graph --oneline`](doc/assets/img/unclean-merge-log.png)

## Branch Policy

The main ideas behind the branching strategy explained here are:
* Keep things as simple as possible.
* The contributors are fully responsible of their changes.
* The contributors are expected to work on top of the latest version of the 
  code.

By following these ideas, the project `main` branch is the place to go to get
the latest changes. The `main` branch is as stable as the testing performed on
each Pull Request before merging it into master.

**For more stable versions, we use tags and releases**. Each release is
associated to a tag in the repository, so it's easy to get the snapshot of each release if needed.

In case of a bug, it will be fixed on the current `main` branch and not 
backported. **Users are expected to be always in the latest release**.

This means that most of the time there will be just one branch upstream,
the rest will be part of the contributors' forks.


## Contribution Guidelines

General GitHub workflow rules for contributing via fork apply to our project.

On top of those, the following is a quick reference of the steps 
([see also an example of the process](doc/pull_request_example.md)):

* Fork the project. See [GitHub documentation on forking a repo](https://docs.github.com/en/github/getting-started-with-github/fork-a-repo)). 
  Make sure you configure the upstream repo as a remote so you will be able to 
  fetch newer changes from upstream later on, if needed.
* Create a local branch (`git checkout -b <branch_name>`).
* Make your changes. Please, follow the
  [Additional Documentation](#additional-documentation).
* Push your local branch to your fork (not to upstream, in the worst case you
  won't have push permission upstream and will get an error, unless you are a 
  trusted committer, in which case please double check your command line).
* Go to GitHub, create the Pull Request. See [GitHub documentation on how to 
  create a Pull Request from a fork](https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork).
  
  * The **contributor** is responsible of providing commits that allow 
  [clean merges](#clean-merge). In case this not happens, they will be requested
  by the reviewers to rebase their branch and push again the changes.
  * The **reviewer** is responsible of merging changes, even if the contributor 
  has permissions to do it. Merges should look like the following one (obtained 
  via `git log --graph --oneline` command):
![Clean and clear merge seen from `git log --graph --oneline`](doc/assets/img/merge-log.png)
  
  * From the merge, is clear:
    * Where the merge was performed.
    * Who merged the changes (not in the image because `--oneline` option was 
    used to summarize the resulting graph).
    * The commits being merged.
    * Who sent those commits (not in the image because `--oneline` option was 
    used to summarize the resulting graph).
    * Ideally only one feature is covered by all of them, no matter if it's 
    split into several commits for clarity, because the tree is clear enough 
    thanks to its shape.

## Additional Documentation
In addition to all of the above mentioned, we encourage you to read the 
following guides before start contributing:

* [How to Write a Git Commit Message](https://chris.beams.io/posts/git-commit/).
  Commit messages matter. Here's how to write them well. Written by Chris Beams.
* [Git Branching - Branches in a Nutshell](https://git-scm.com/book/en/v2/Git-Branching-Branches-in-a-Nutshell). From 
  [Pro Git book](https://git-scm.com/book/en/v2), written by Scott Chacon 
  and Ben Straub and published by Apress. All content is licensed under the 
  Creative Commons Attribution Non Commercial Share Alike 3.0 license.
* [Git happens! 6 Common Git mistakes and how to fix them](https://about.gitlab.com/blog/2018/08/08/git-happens/). Written by Sam Beckham.