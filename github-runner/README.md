####

Install rest app

```shell
kubectl create namespace github
argocd app create cert-manager --repo https://github.com/stokilo/argocd.git --path cert-manager --dest-server https://kubernetes.default.svc --dest-namespace github
```
