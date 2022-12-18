####

Install tekton pipelines

```shell
argocd app create tekton-pipeline --repo https://github.com/stokilo/argocd.git --path tekton/pipelines --dest-server https://kubernetes.default.svc --dest-namespace default
```
