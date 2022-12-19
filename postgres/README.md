####

Install rest app

```shell
kubectl create namespace postgres-operator
kubectl create namespace postgresql
argocd app create postgres-repo --repo https://github.com/stokilo/argocd.git --path postgres/operator --dest-server https://kubernetes.default.svc --dest-namespace postgres-operator
argocd app create postgres-ui --repo https://github.com/stokilo/argocd.git --path postgres/ui --dest-server https://kubernetes.default.svc --dest-namespace postgresql
argocd app create postgres-cluster --repo https://github.com/stokilo/argocd.git --path postgres/cluster --dest-server https://kubernetes.default.svc --dest-namespace postgresql
```
