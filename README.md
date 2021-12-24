# Installing Kyverno

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

[Installation](https://kyverno.io/docs/kyverno-cli/#install-via-krew)

`kubectl-kyverno test resources`
