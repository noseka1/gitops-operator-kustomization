# Kustomization for deploying Red Hat OpenShift GitOps operator to OpenShift

## Quick start

Install Red Hat OpenShift GitOps operator by issuing the command:

```
$ oc apply --kustomize gitops-operator/base
```

When the Argo CD instance deployment is complete, the `phase` filed in the instance status will read `Available` like this:

```
$ oc get argocd \
  --namespace openshift-gitops \
  argocd-cluster \
  --output jsonpath='{.status.phase}'
Available
```
