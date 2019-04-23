# Git Guidelines

## Git Commit and Merge Guidelines
- Don’t leave WIPs in the branch history: squash them before merging your code back to develop or master. See the “Useful GIT Tools” section for how to add a set of git shortcuts for dealing with WIPs.
    - At the end of the day use `git wip`
    - At the start of each day use `git unwip`
    - It’s reasonable and even encouraged to have a test failing in a WIP so you know where to start again
    - It can be helpful to create a manual WIP with a list of todos
- For large stories that span multiple days, try to create useful real commits (not WIPs) as chunks of functionality get completed. If it is excessively large, see if the story's scope can be reduced instead.
- Real commits that are kept in history before merging should have all tests passing and be safe to deploy.
- If possible, rebase the main repository branch under your feature changes before merging. This results in a cleaner history that is easier to follow and work with.
- Rebase at least daily, in the morning. This will make your final rebase and merge much easier to deal with.
- ALWAYS run the unit and functional tests after rebasing and merging, before pushing to the remote repo.
- Structure your commit messages in the following style (excluding WIP):
    - The first line of the message should be a single sentence summarizing the changes being made. It usually should relate to the story title
    - Then include a detailed explanation of the changes and a bulleted list of specific details that you deem useful for the future
    - Finally the story number in brackets (i.e. [SE-414])

```
Implemented example commit message for coding standards.

Built out the list of requirements and added the to the doc:
* Built a bulleted list of the rules
* Created this example commit message
* Some other details that are useful
[SE-414]
```

## Git Commit Template
A template can be configured so that each commit begins with a pre-populated message to help make using the commit message standards easier. In sourcetree, click: Sourcetree -> Preferences -> Commit Template. An example template is as follows:

```
WIP
 *
[SE-]
```

Alternatively, you can create a .stCommitMsg in your home directory, then enable the commit via the global git config by adding the line:

```
[commit]
        template = /Users/<user>/.stCommitMsg
```

## Git Branch Management
There are two primary branch management strategies that should be followed:
1. Individual Feature Development
1. Hotfix Bug Development

In both scenarios, completed work should be merged into the repository’s mainline branch (“master”) only after the Engineer has verified that the feature is complete (see DoD above).

### Individual Feature Development
When beginning work on these stories a feature branch that begins with the story number followed by a meaningful description should be created off the current mainline branch’s top commit. As work is completed please ensure the commits saved in the feature branch represent “safe” states of code that could be independently deployed. If the commit could not be deployed as the top commit of a release, then it must be a WIP. Make use of the [git rebase](https://onlywei.github.io/explain-git-with-d3/#rebase) feature to squash all WIP commits together. Ideally for all features the entire set of changes are committed in a single git commit.

Upon completion of the feature it should be merged directly back to the mainline branch (which should then be re-deployed to a test environment before marking the story as Delivered). Before executing this merge you should rebase the current state of the mainline branch below all of the feature branch’s commits.

### Hotfix Bug Development
Hotfix bug development should follow a similar pattern as the Individual Feature Development, except it should always be branched off the top of the “master” branch at the last commit’s git tag. Create a branch with the naming convention of “hotfix/v{major}.{minor}.{patch}”. 

The last commit of the hotfix branch needs to update all version numbers necessary (usually in the “package.json” file, sometimes in other files also depending on the project.

For testing, get the hotfix branch itself deployed to one of the testing environments. Upon completion of testing it will also be merged back onto the “master” branch for immediate release.

Upon release of a hotfix, the area of the system that was touched by the code communicated with Support (or the reporter of the original issue) so it can be validated and monitored for an appropriate time period depending on the circumstances.
