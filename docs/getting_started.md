Getting started
===============

## Setup the development environment

To set up the development environment, you will need to install __pyenv__ on your computer. You can find installation instruction at [https://github.com/pyenv/pyenv#installation](https://github.com/pyenv/pyenv#installation).

When __pyenv__ is installed, you can run `make setup` to configure the Python environment for this project, including development tools and dependencies.

Additionally, you will need to install __speccy__ for building specific services. __Speccy__ is used to merge OpenAPI definitions together for API Gateway. You can find installation instruction at [https://github.com/wework/speccy#setup](https://github.com/wework/speccy#setup).

## Deploy the infrastructure on AWS

If you want to deploy the entire project into your AWS account in a dev environment, you can run the command `make all` in the [root](../) of this project.

If you want to deploy only a specific service and its dependencies, you can use the command `make deps-${SERVICE}`.

These commands will lint, build, run unit tests, package, deploy and run integration tests on the services.

### Deploy the production pipeline

If you want to deploy a complete pipeline to a production environment, you can run `make bootstrap-pipeline`, which will deploy all services in all environments needed by the pipeline, the CI/CD pipeline itself and seed a CodeCommit repository with the latest commit from this repository.

When you want to push modifications to AWS, you can run `git push aws HEAD:master`, which will push the latest commit from the current branch to the master branch in the CodeCommit repository.

## Creating or modifying a service

To read how you can create a new service or modify an existing one, please read the [service structure documentation](service.md).