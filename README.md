# Gitlab Cookbook

- [Gitlab Cookbook](#gitlab-cookbook)
  - [Introduction](#introduction)
  - [Continous Integration](#continous-integration)
  - [Levels of Testing](#levels-of-testing)
- [Tips](#tips)
  - [Execution from container](#execution-from-container)
  - [Git pager configuration](#git-pager-configuration)

## Introduction

Gitlab is a popular open-source software that provides users a platform for collaboration, software version control as well as Continuous Integration/Continious Delivery (CI/CD) capabilities.

## Continous Integration

Continuous Integration
- Merge frequently
- QA when code is ready
- Developer driven

Non-Continuous Integration
- Merge everything at once
- QA all of the changes at once
- Schedule and deadline driven

Automated tests are essential to CI.

## Levels of Testing

- Syntax testing and linting
- Unit and integration testing
- Acceptance testing

# Tips

## Execution from container

```bash
# Generate a static website and store it on host machine
sudo docker run --rm --volume="$PWD:/srv/jekyll" -it jekyll/jekyll:3.8 jekyll new blog
```

## Git pager configuration

Works for `.log`, `.branch`.

```bash
# For current repository log
git config pager.log false

# For all repositories log
git config --global pager.log false
```