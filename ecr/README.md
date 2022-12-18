####

Private AWS container registry ECR mandates token authentication.
Token is valid for 12 hours. It must be regenerated through K8s Cron Job.

Steps:

1. Create IAM user (ecr-user) with R+W access to ECR. 
2. Generate access key for ecr-user.
3. Export credentials to secret

```shell
export AWS_ACCESS_KEY_ID=AKIAT.....
export AWS_SECRET_ACCESS_KEY=G6....
```

Test ecr-user credentials works as expected

```shell
aws ecr get-login-password --region eu-central-1
```

4. Create K8s secret in target namespace to store:
   AWS_ACCESS_KEY_ID and AWS_SECRET_ACCESS_KEY

```shell
kubectl create secret generic ecr-iam \
 --from-literal='AWS_ACCESS_KEY_ID=AK..' \
  --from-literal='AWS_SECRET_ACCESS_KEY=G6..' \
  -n default
```

5. Install ecr.yaml app

```shell
argocd app create ecr-sync --repo https://github.com/stokilo/argocd.git --path ecr --dest-server https://kubernetes.default.svc --dest-namespace default
```
