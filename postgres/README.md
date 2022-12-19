####

Install rest app

```shell
kubectl create namespace postgres
argocd app create postgres-repo --repo https://github.com/stokilo/argocd.git --path postgres/operator--dest-server https://kubernetes.default.svc --dest-namespace postgres
argocd app create postgres-ui --repo https://github.com/stokilo/argocd.git --path postgres/ui--dest-server https://kubernetes.default.svc --dest-namespace postgres
```
