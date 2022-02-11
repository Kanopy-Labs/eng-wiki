# Github & Version Control

- [Github & Version Control](#github--version-control)
  - [Rebasing vs Merging](#rebasing-vs-merging)
    - [When should I be merging commits?](#when-should-i-be-merging-commits)
    - [When should I be rebase commits?](#when-should-i-be-rebase-commits)
  - [Pull Requests](#pull-requests)
    - [Why should I use pull requests?](#why-should-i-use-pull-requests)
    - [What are github actions?](#what-are-github-actions)
    - [What should I do before merging a pull request?](#what-should-i-do-before-merging-a-pull-request)
    - [Who should I request to review my pull request?](#who-should-i-request-to-review-my-pull-request)
    - [How should I be reviewing code?](#how-should-i-be-reviewing-code)
  - [Branching](#branching)
    - [How do I create a new branch?](#how-do-i-create-a-new-branch)
    - [What should my base branch be?](#what-should-my-base-branch-be)
    - [What should I name my branch?](#what-should-i-name-my-branch)
  - [Commit](#commit)
    - [What are commits?](#what-are-commits)
    - [How do I create a commit?](#how-do-i-create-a-commit)
    - [How should I name my commit messages?](#how-should-i-name-my-commit-messages)
  - [Reverting a change](#reverting-a-change)
    - [How do I revert a change?](#how-do-i-revert-a-change)
  - [Merge Conflicts](#merge-conflicts)
    - [How should I be handling merge conflicts](#how-should-i-be-handling-merge-conflicts)
    - [What are the incoming vs current changes?](#what-are-the-incoming-vs-current-changes)
  - [Additional Resources](#additional-resources)

---

## Rebasing vs Merging

### When should I be merging commits?

You should be merging commits when you push a PR into `main`. You can also use merge to get commits from a specific branch onto another one.

### When should I be rebase commits?

Rebasing can cause us to destory commits. We should attempt to not rebase unless necessary. Merging is much safer in 95% of scenarios. Here is some more information of [merging vs. rebasing](https://hackernoon.com/git-merge-vs-rebase-whats-the-diff-76413c117333).

## Pull Requests

### Why should I use pull requests?

This let's us add a layer of QA before any code is pushed to the `main` branch and deployed. This let's us improve the overall quality of our code because it is always peer reviewed.

### What are github actions?

GitHub actions let us add commands that are run everytime code is pushed up to GitHub. This is commonly referred to as continuous integration and continuous deployment. This let's us run tests, linting, and other sanity checks before the code is pushed to ensure as much security as possible on the code. The more detail your GitHub actions are, the more security you'll provide to your code.

### What should I do before merging a pull request?

Some good practices before merging are:
* Perform a self-review
* Test it
* Pull main so it is up to date
* Write a description of what/why/how you did
* Add images if any significant UI changes
* Get it approved by someone else
* Ensure CI/CD passes

### Who should I request to review my pull request?

There will be automatic suggested reviewers or people that have context on the specific feature.

### How should I be reviewing code?

When reviewing:
* Read description
* Think how you would do it yourself
* Nit picking (are the files in the right place)
* Check if there are tests that cover the added functionality

## Branching

### How do I create a new branch?

```sh
$ git checkout -b [BRANCH NAME]
```

### What should my base branch be?

When working on many feature branches, it is okay to branch off that to work on sub-features.

### What should I name my branch?

If you have a Linear integration, you can use the names for that: `[YOUR_NAME]/[TASK_NUMBER]-[TASK_TITLE]`. If Linear isn't in place, it's fine to use an issue number or just rid the number entirely.

## Commit

### What are commits?

A commit is a change or revision in git's terminology for a file or set of files. This adds it to the git history.

### How do I create a commit?

Add your changes and then commit with a message.

```sh
$ git add .
$ git commit -m "adds [SPECIFIC FEATURE]"
```

### How should I name my commit messages?

It's good practice to view commits as changing the state of the code so being able to read through all the messages and understand how each changes the codebase. Good practice is to use a verb (like `adds`, `fixes`, `changes`) followed by a brief summary of the change. Try to keep commit messages shorter.

## Reverting a change

Reverting is basically the equivalent of the undo command in git.

### How do I revert a change?

Revert is documented more in detail [here](https://git-scm.com/docs/git-revert). If you want to just undo a specific change, you can run:

```sh
$ git revert HEAD~1
```

## Merge Conflicts

### How should I be handling merge conflicts

It's good to go through line by line and address differences to ensure the code still works. Then make sure to run and test the code after to make sure it didn't end up breaking. GitHub and VSCodes both have UIs that simplify this process compared to doing it directly in the command line.

### What are the incoming vs current changes?

Merge conflicts include incoming and current changes. Incoming are ones from the branch you are merging to and current is your current local changes.

## Additional Resources

* [Git Simple Guide / Cheat Sheet](https://rogerdudler.github.io/git-guide/)
* [Learn Git Interactively](https://learngitbranching.js.org/?locale=en_US)
* [PR Etiquette](https://gist.github.com/mikepea/863f63d6e37281e329f8)
