# Mergify

Mergify is a tool to merge changes from a branch one commit at a time.  This
is most useful when merging changes to a highly diverged fork of a project.

```
usage:
    mergify start [-p <pause-expression>] <branch>
    mergify abort
    mergify continue
    mergify status
```

## Commands
 * start

	Begin mergin *branch* to the current branch.  All changes since the
	common parent will be merged one change at a time.  If merge
	fails, mergify exits to allow the user to correct the merge.

	pause-expression is a regular expression that matches modified paths.
	When it matches, mergify stops before committing the merged change
	even if no conflict occurs.

 * abort

	Abandon the current merge process.  Previously merged changes are not
        reverted, but a revision is provided as a target for git reset.

 * continue

	Commit the resolved change and continue the merging process.

 * status

	Show the current merge status.


