# A test for the `rebase` functionality.

This repo is for testing the `rebase` functionality in a specific use case. It's about rebase then push.

## Testing scenario

Test what will happen in the following scenario:

1. The main branch is at `39e92eac`, then a `test_rebase` branch is created based on this commit.

1. Some modification is made at the `test_rebase` branch, the commit hash is `79b7ee5f`. And it's committed and pushed to the github repo.

1. Some new modification is made at the `main` branch and pushed to the github repo, with commit hash `78a32b6`.

Hence we have the following branch figure at the github repo:

main:        `39e92eac` --> `78a32b6`
                 |
test_branch: `79bee5f`

At this moment, if I want to update my `test_branch` with the latest development from `main` branch without adding too many merge commits, I can use the `rebase` option.

__Note:__ just keep in mind, `rebase` is not moving your `79bee5f` in the `test_branch` to a new base in `main`. It will COPY the content in `79bee5f` and PASTE(create a new commit) with its base at `78a32b6` of main branch.

And the result is:

main:        `39e92eac` --> `78a32b6`
                                |
test_branch: {`79bee5f`}    `d89c4d9d`

Therefore the `test_branch` history has been changed from:

`39e92eac` --> `79bee5f`

to 

`39e92eac` --> `78a32b6` --> `d89c4d9d`

And this is a diverged history on the same branch. 

When you push the new local `test_branch` history to the github repo, it will report the divergency and you have to __force push__ hence change the history of github repo.
