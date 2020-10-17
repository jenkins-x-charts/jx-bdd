## jx bdd

This is a helm chart for running the Jenkins X BDD tests in a cluster to verify your installation

## Installing 

Make sure you have the `jx3` helm repository added:
```bash
helm repo add jx3 https://storage.googleapis.com/jenkinsxio/charts
```     

To install the helm chart you need to specify some values:

```bash          
helm install bdd jx3/jx-bdd --set bdd.username=$GIT_USERNAME --set bdd.token=$GIT_TOKEN
```

You can view the logs via:

```bash
kubectl logs -f -l app=jx-bdd
```

To terminate the BDD tests

```bash          
helm delete bdd
```

