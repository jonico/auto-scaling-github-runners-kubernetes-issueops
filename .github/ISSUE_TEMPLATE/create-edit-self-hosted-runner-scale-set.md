---
name: Create or edit self-hosted runner scale set
about: Create or edit a self-hosted runner scale set you can use for a workflow
title: Self-hosted runner scale set create/update request for <insert env>
labels: 'self-hosted-runner-scale-set'

---

Issue created by this issue template will create or edit the necessary Kubernetes configuration needed for a self-hosted runner scale set running in its own Kubernetes namespace operated by the [summerwind/actions-runner-controller](https://github.com/summerwind/actions-runner-controller).


Please insert the runner configuration values in the JSON below. It is advised but not mandatory that you create a runner group with the name of your environment first to control which repositories have access to your runner scale set.

**Because this setup is using a quite small Kubernetes cluster and we like to avoid process churn, please do not set the number of `maxRunners` per environment greater than 16.**

```json
{
  "environment": "<enter an environment name here>",
  "organization": "<enter a GitHub organization name here>",
  "minRunners": "2",
  "maxRunners": "5",
  "runnerImage": "jonico/actions-runner:latest",
  "runnerGroup": "default",
  "dockerEnabled": "false",
  "cloud": "gcp"
}
```
