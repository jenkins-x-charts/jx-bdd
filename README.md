## jx bdd

This is a helm chart for running the Jenkins X BDD tests in a cluster

## Installing 

To install the helm chart you need to specify some values:

```bash 
helm install bdd . --set bdd.username=$GIT_USERNAME --set bdd.token=$GIT_TOKEN
```

