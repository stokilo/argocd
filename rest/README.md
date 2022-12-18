####

Install rest app

```shell
argocd app create rest --repo https://github.com/stokilo/argocd.git --path rest --dest-server https://kubernetes.default.svc --dest-namespace default
```
