---
name: Delete self-hosted runner scale set
about: Deletes and archives a self-hosted runner scale set
title: Self-hosted runner scale set delete/archive request for <insert env>
labels: 'delete-self-hosted-runner-scale-set'

---

Issue created by this issue template will delete and archive the Kubernetes configuration associated with the self-hosted runner scale set operated by the [summerwind/actions-runner-controller](https://github.com/summerwind/actions-runner-controller).


Please insert the runner configuration values in the JSON below.
```json
{
  "environment": "<enter the environment to delete here>",
  "cloud": "gcp"
}
```
