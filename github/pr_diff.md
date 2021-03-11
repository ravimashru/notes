# Diffs in PRs

Topic branch = branch from which you are opening a PR.

Base branch = branch you want to merge changes to.

When a PR is opened on GitHub, the diff shown is a **three-dot diff**. This diff shows the most recent version of the topic branch diff-ed with the commit where the topic branch was last synced with the base branch.





![](./images/diff1.png)

When a PR is opened from the topic branch to the base branch, the diff shown will be between commits A and B.







![](./images/diff2.png)

When a PR is opened from the topic branch to the base branch in this case, the diff shown is between commits A and B (because A is the last commit when the base branch was last synced with the topic branch), and not between commits C and B.

To see a diff between B and C, there are two options:

1. Update the topic branch from the base branch so that the last commit when the two branches were synced is updated to this new commit.
2. See a diff between the two latest commits on both branches directly using the following endpoint: `https://github.com/<org_or_user>/<repo>/compare/<commit1>..<commit2>`

Note: when using the second approach, the commits made in the branch with `commit1` will be shown as **deletions** in the diff since technically, you need to delete those diffs to go from `commit1` to the latest common ancestor commit, and then reach `commit2`.

References:

- [GitHub's Pull Request documentation](https://help.github.com/en/articles/about-comparing-branches-in-pull-requests)

