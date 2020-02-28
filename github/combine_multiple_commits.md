# Combine Multiple Commits

Step 1: Use `git rebase` in interactive mode with the parent commit (the commit you would like to start merging from).

```
$ git rebase -i <parent_commit_it>
```

Example:
```
git rebase -i HEAD~3
```
This will attempt to merge the last three commits into one.

Step 2: In the next screen, `pick` the first commit and `squash` the rest.

Step 3: Edit the commit message.

Reference: https://www.w3docs.com/snippets/git/how-to-combine-multiple-commits-into-one-with-3-steps.html
