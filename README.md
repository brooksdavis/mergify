# Mergify

Mergify is a tool to merge changes from a branch one commit at a time.  This
is most useful when merging changes to a highly diverged fork of a project.

```
usage:
    mergify start [<options>] <branch>
    mergify abort
    mergify autoadd
    mergify commit
    mergify continue
    mergify show
    mergify status
```

## Commands
 * start

	Begin mergin *branch* to the current branch.  All changes since the
	common parent will be merged one change at a time.  If merge
	fails, mergify exits to allow the user to correct the merge.

	Options:

	-c <list-of-hashes>

	Stop when any of the hashes in the space-separated list of hashes has
	been merged.

	-p <pause-expression>

	Paths to files modified by the commit are matched against the
	expression.  If it matches, mergify stops before committing the merged
	commit.

	-s

	Begin the merge, but end after the first commit.

 * abort

	Abandon the current merge process.  Previously merged changes are not
        reverted, but a revision is provided as a target for git reset.

 * autoadd

	Add changed files that do not contain conflict markers.

	Also delete files that were deleted from this tree in a prior commit
	and changed upstream.

 * commit

	Commit the resolved change and exit.

 * continue

	Commit the resolved change and continue the merging process.

 * show

	Show the contents of the commit being merged.

 * status

	Show the current merge status.


