####

Install tekton

```shell
argocd app create tekton --repo https://github.com/stokilo/argocd.git --path tekton --dest-server https://kubernetes.default.svc --dest-namespace default
```
