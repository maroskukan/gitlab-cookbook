# Gitlab Cookbook

- [Gitlab Cookbook](#gitlab-cookbook)
  - [Introduction](#introduction)
  - [Continous Integration](#continous-integration)
  - [Levels of Testing](#levels-of-testing)
  - [Continous Delivery](#continous-delivery)
    - [Environmnets](#environmnets)
    - [Code Promotion](#code-promotion)
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


## Continous Delivery

### Environmnets

- Standalone hardware and software stack
- Capable of running your entire application
- Configured for a specific puspose:
  - Dev - (One environment per developer, easily to repaiar or replace, lower resources requirements)
  - QA - (Shared environment, intended for testing, automated test, similar to prod but not identical)
  - Staging - (Clone of production, only change as part of prod release, test in prod without releasing to prod)
  - Prod - (Customer facing servers, part of CD pipeline, automated tests, siple to roll out and back)

### Code Promotion

- Feature branches developed in development and tested in QA
- Long-running development branch
- Development branch is tested in QA
- Release is "cut" and pushed to staging
- Release is tagged and pushed to production


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