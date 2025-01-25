# A test for the `rebase` functionality.

This repo is for testing the `rebase` functionality in a specific use case. It's about rebase then push.

## Testing scenario

Test what will happen in the following scenario:

1. The main branch is at `39e92eac`, then a `test_rebase` branch is created based on this commit.

1. Some modification is made at the `test_rebase` branch, committed and pushed to the github repo.

1. Some modification is made at the `test_rebase` branch, the commit hash is `79b7ee5f`. And it's committed and pushed to the github repo.

1. Some new modification is made at the `main` branch and pushed to the github repo.

