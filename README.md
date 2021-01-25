# setup-self-hosted-runner-kubernetes-cluster

IssueOps example on how to set up an autoscaling, self-hosted runner fleet in kubernetes using [summerwind/actions-runner-controller](https://github.com/summerwind/actions-runner-controller).

In order to setup or modify an auto-scaling runner set, just [create an issue](https://octodemo.com/baseline/setup-self-hosted-runner-kubernetes-cluster/issues/new/choose):

![image](https://user-images.githubusercontent.com/1872314/107054578-9d9b6f00-67d0-11eb-88ed-fe836c687b31.png)

and /approve the Kubernetes config changes in the resulting pull request:

![image](https://media.octodemo.com/user/306/files/3422ae80-60b4-11eb-8ffe-432a79f46f9c)

The resulting pull request also contains a workflow file snippet to test your newly created runner group:

![image](https://media.octodemo.com/user/306/files/f2e5cb00-60c2-11eb-8207-3c25ed268bfc)

## Using custom images

In order to use your own Docker runner images, follow the suggestions [here](https://github.com/summerwind/actions-runner-controller#software-installed-in-the-runner-image).
The Dockerfile used to produce the default image for the issue template has been checked into [this repository](runner/Dockerfile).

# Setting up a copy of this IssueOps based repository

If you like to work directly with this repository, there is no further need but to follow the comments in the issues created by the template and the approved PR.

If you like to setup a copy of this repository somewhere else, you would need to install the actions-runner controller in a Kubernetes cluster as described [here](https://github.com/summerwind/actions-runner-controller#installation).

While most code in this IssueOps example has been written to be cloud agnostic, the part to authenticate to the cluster is currently specific to GCP. If you are also using GCP, set the following GitHub Action credentials to authenticate to the cluster:

* CLUSTER_LOCATION: GCP cluster location where you setup the actions-runner controller
* CLUSTER_NAME: GCP cluster name
* GCP_SA_KEY: GCP service account with permissions to create new namespaces and objects within
* PROJECT_ID: GCP project id of your cluster

If you are using a different cloud, you would only need to [adjust the steps](.github/workflows/approve-self-hosted-runner-create-edit.yaml) needed to get to the point where your runner can successfully execute kubectl commands - pull requests are welcome :octocat: :heart:

### Needed issue labels

Last but not least, you would need to create two labels in the copy of this repository: `self-hosted-runner-scale-set` and `delete-self-hosted-runner-scale-set`
