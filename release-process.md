# Release Process
When preparing a standard release, do the following steps:

- Branch the release branch off of the desired commit, naming it in the “release/v{major}.{minor}.{patch}” convention.
- Bump the version number within the release branch, run npm shrinkwrap to update the shrinkwrap file also. Commit these two file changes to the repo.
- Assist Application Support in verifying which Tracker stories are in the release, tagging said stories with a “{project}-v{major}.{minor}.{patch}” label.
- Assist Application Support in creating the Release documentation, including the inclusion of all Pre and Post Deployment Actions in the documentation.
- Deploy the release branch to the Staging environment, in coordination with the QA team. Follow the Release documentation exactly.
- Once all regression testing is completed, at the request of Application Support, merge the release branch into “master”.
    - Create a git tag in the format of “v{major}.{minor}.{patch}” on the merged master commit.
    - Merge the updated master branch back into develop if present (rebase if possible).
    - Clean up fully merged, release feature, epic, and release branches in git.
- Review the final git state with Application Support.
- Application Support will execute the production deployment using the release’s git tag.

For hotfix releases, the same general process should be followed, except the branch name should be in the format of “hotfix/v{major}.{minor}.{patch}” (as stated above in the Git Branch Management section.
