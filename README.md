# Changelog

Important changes according to the version they are release in.

## 2.2.0

- Updates all github actions in the workflow

## 2.1.3

- Workflow: docker-build-release.yml
  -  Adds an optional input argument `build_args` for the docker build-args
     argument. This enables us to use more docker file arguments in the novomind
     hosted services.


# Workflows
## `azure-docker-build-release.yml`
Build a docker image and push it to Azure container registry. See the workflow file itself for possible/required inputs and secrets.

This workflow authenticates with Azure through OIDC using OAuth2 client credentials workflow. You need to pass `azure_client_id`, `azure_client_secret`, `azure_tenant_id` and `azure_subscription_id` as **secrets** to the workflow, which you should inject using [Github Action Secrets](https://docs.github.com/en/actions/security-guides/encrypted-secrets).

## `docker-build-release.yml`
Build a docker image and push it to a container registry. See the workflow file itself for possible/required inputs and secrets.

## `docker-test.yml`
**DEPRECATED!**
Do not use this action anymore. Implement a dedicated go test workflow or copy
it from a project that has a test workflow already implemented.

~~Build a docker container and run tests inside that container. See the workflow file itself for possible/required inputs and secrets.~~

## `deploy-aks.yml`
Deploys the manifests stored in the repository into an azure aks cluster. See
the workflow file itself for possible/required inputs and secrets and examples.
