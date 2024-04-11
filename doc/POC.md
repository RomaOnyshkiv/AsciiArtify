# Install ArgoCD

### 1. Start minikube
```shell
minikube start
```

### 2. Check minikube
```shell
minikube status
```

### 3. Install ArgoCD
```shell
kubectl create namespace argocd && kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### 4. Check status

```shell
kubectl get all -A
```

### 5. Run ArgoCD
```shell
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

### 6. Get pass
```shell
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}"|base64 -d;echo
```


### ArgoCD demo
<img src="../data/argoCD.gif" width="900" height="570" />
