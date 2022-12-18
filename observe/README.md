####

Install rest app

```shell
kubectl create namespace observe
argocd app create observe --repo https://github.com/stokilo/argocd.git --path observe --dest-server https://kubernetes.default.svc --dest-namespace observe
argocd app create observe --repo https://github.com/stokilo/argocd.git --path observe/loki --dest-server https://kubernetes.default.svc --dest-namespace observe
```
