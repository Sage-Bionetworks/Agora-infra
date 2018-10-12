# Overview
Infrastructure for the [Agora](https://github.com/Sage-Bionetworks/Agora)
application.


# Purpose
This repo contains infrastructure templates to for the Agora application.
It is also setup with CI/CD to automatically deploy the infrastructure
to AWS.


# Workflow
There is a specific workflow for making changes to the infrastructure.
* Make pull requests to this repo
* Get someone to review and approve your changes
* Change is merged after being approved
* Travis runs a build to test the infrastructure templates
* Travis deploys the infrastructure updates to AWS


## Continuous Integration
We have configured Travis to deploy CF template updates.  Travis deploys using
[sceptre](https://sceptre.cloudreach.com/latest/about.html)


# Contributions

## Issues
* https://sagebionetworks.jira.com/projects/IT

## Builds
* https://travis-ci.org/Sage-Bionetworks/agora-infra

## Secrets
* We use the [AWS SSM](https://docs.aws.amazon.com/systems-manager/latest/userguide/systems-manager-paramstore.html)
to store secrets for this project.  Sceptre retrieves the secrets using
a [sceptre ssm resolver](https://github.com/cloudreach/sceptre/tree/v1/contrib/ssm-resolver)
and passes them to the cloudformation stack on deployment.
