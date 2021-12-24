# Installing Kyverno

## Pre Requisites

- Digital Ocean Kubernetes Cluster
- Digital Ocean Container Registry
- [doctl](https://docs.digitalocean.com/reference/doctl/how-to/install/)
- [Helm](https://helm.sh/docs/intro/install/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/#kubectl)
- (Optional) [Kyverno CLI](https://kyverno.io/docs/kyverno-cli/)

## Upload sample image to DOCR

```
docker tag e7d168d7db45 registry.digitalocean.com/do-sfo3-k8s-1-21-5-do-cezar-bernardi/busybox:latest
docker image push registry.digitalocean.com/do-sfo3-k8s-1-21-5-do-cezar-bernardi/busybox:latest
```

## Add Kyverno Helm Chart Repo

```
helm repo add kyverno https://kyverno.github.io/kyverno/
helm repo update
helm install kyverno kyverno/kyverno --namespace kyverno --create-namespace
```

## Create and Apply Kyverno Policies

`kubectl apply -f resources/policies/`

## Create resources in cluster

`kubectl apply -f resources/test-yamls/`

### Use Kyverno CLI to test resources

`kubectl-kyverno test resources`

# Demo

[YouTube Video](https://youtu.be/UwP_NH0-B-I)
