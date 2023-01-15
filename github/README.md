####

Install rest app

```shell
kubectl create namespace github
argocd app create cert-manager --repo https://github.com/stokilo/argocd.git --path github/cert-manager --dest-server https://kubernetes.default.svc --dest-namespace github
argocd app create runner-controller --repo https://github.com/stokilo/argocd.git --path github/runner-controller --dest-server https://kubernetes.default.svc --dest-namespace github
argocd app create rest-db-runner --repo https://github.com/stokilo/argocd.git --path github/rest-db-runner --dest-server https://kubernetes.default.svc --dest-namespace github
```
