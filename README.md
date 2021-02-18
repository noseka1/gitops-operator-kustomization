# Kustomization for deploying Red Hat OpenShift GitOps operator to OpenShift

The OpenShift GitOps operator is based on the [Argo CD Operator](https://github.com/argoproj-labs/argocd-operator). The Argo CD Operator documentation can be found [here](https://argocd-operator.readthedocs.io/en/latest/).

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
