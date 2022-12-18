####

Install rest app

```shell
argocd app create observe --repo https://github.com/stokilo/argocd.git --path observe --dest-server https://kubernetes.default.svc --dest-namespace observe
```
