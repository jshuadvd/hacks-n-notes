# Git

Git notes.

## Git hooks

- [jira git hooks](https://github.com/uptech/git-tools)

## Mac OS Sierra id_rsa passphrase git issue

https://superuser.com/questions/1127067/macos-keeps-asking-my-ssh-passphrase-since-i-updated-to-sierra

## Snippets

### How to count lines of code in a repo

```sh
git ls-files | xargs wc -l
```

## Squash

> To compress multiple commits into a single commit.
> > See reference [blog post](https://ariejan.net/2011/07/05/git-squash-your-latests-commits-into-one/)

- This can be useful to push cleaner branches to pull request.
- Also it might make easier to `git rebase` since it will be just one step instead of multiple steps.

`git rebase -i HEAD~3`

A file will open up in your editor for you to choose which commits to squash and which to leave like that (pick). Change the `pick` keyword to `squash` if you want to squash a particular commit.
Then save to finish the `rebase` (squash).

Only squash commits that haven't been push to origin. Otherwise you would be rewriting history and that can cause painful sync issues.
