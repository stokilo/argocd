####

Install rest app

```shell
argocd app create qk8s --repo https://github.com/stokilo/argocd.git --path qk8s --dest-server https://kubernetes.default.svc --dest-namespace default
```
