# Welcome to [PROJECT NAME] contributing guide

In this guide you will get an overview of the contribution workflow from opening an issue, branch naming convention, creating a PR, reviewing, merging the PR etc.

# Getting Started #

To use our project, make sure you have all tools and dependencies installed on your local machine with the right versions following the [README.md](../README.md)

### Branch Name

The branch name should contain at least the jira task number, the type of the work what the developer will realise from the list below:

- feat
- fix
- chore
- infra

The developer should follow the branch naming convention as described below, because that will be on the criteria to the PR be approved.

```
// [JIRA_TASK_NUMBER]/[TYPE]/meaningful-name-to-describe-the-task 
SP-333/feat/add-login-page
SP-333/fix/crash-on-user-login
```

### Commit messages

The commits should follow the pattern from [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)

Basically the commit message should be like:

```
<type>[optional scope]: <description>
-- empty line
[optional body]
-- empty line
[optional footer(s)]
```

example 1:
```
chore!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

example 2:
```
feat(lang): add Polish language
```

example 3:
```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.

Reviewed-by: Z
Refs: #123
```

The list of the possible types:

- build
- chore
- ci
- docs
- feat
- fix
- perf
- refactor
- revert
- style
- test

### Pull Request titles

The title should follow the following conventions:

````
// [TYPE]([JIRA_TASK_NUMBER]): [MEANINGFUL_DESCRIPTION]
fix(PROJECT-KEY-ISSUE-ID): fix typos and text formatting
feat(PROJECT-KEY-ISSUE-ID): add user sing in
````

### Creating a Pull Request

All contributions are handled via Pull Requests. The developer's PR should target [master](https://github.com/bitwise-technology/bw-project-template/tree/master) 
branch. This branch is the place where we aggregate all upcoming changes for the next release to the [PROJECT-NAME] 
web/mobile/desktop app. Moreover, your PR must pass all tests and provide a meaningful description of what it is about.

Before opening a PR please make sure all tests are passing using the command ```npm run test:coverage```([REPLACE THE COMMAND]) is passing, 
otherwise, the PR will not be reviewed. Once the tests pass, you can push your feature branch to the GitHub repository, 
then open a pull request. There are some best practices that will be followed during the development of this project 
defined by our team members.

Quick checklist summary before submitting a PR:

- 🎉 Make sure tests are added or updated to your changes. When possible, add tests to verify bug fixes and prevent 
future regressions.
- 📖 Check that you provided a README entry documenting your changes when necessary, in most cases is when something 
changes to have the project working, building or even when some tool is added and needs an explanation of how to run it.
- 🚨 Verify that tests pass
- 🚀 Push it!
- 🧐 Make sure to follow the [TEMPLATE](../.github/PULL_REQUEST_TEMPLATE.md) while creating your PR, if the developer 
does not follow the suggested template the PR will not be accepted. 
