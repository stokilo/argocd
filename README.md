#### Installation

Follow argo [basic installation guid](https://argo-cd.readthedocs.io/en/stable/getting_started/)

Then each folder contains argo application, start in order i.e. for vault:

```shell
kubectl create namespace vault
argocd app create vault --repo https://github.com/stokilo/argocd.git \ 
 --path vault --dest-server https://kubernetes.default.svc --dest-namespace vault
```

1. ecr - sync aws credentials to access ecr registry
2. rest - rest api fetching container image from private registry
3. vault, vault argo plugin
