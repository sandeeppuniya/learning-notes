# learning-notes

Contains useful notes on new learning stuff.

## ArgoCd

1. Deploy ArgoCD Command:

```
   kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

2. Make argocd-server accept traffic:

```
kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "NodePort"}}'
```

3. Get ArgoCD Secret

```
username: admin
password: <value from command below>

kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d && echo
```