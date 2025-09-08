# Kubernetes
Yaml's for Cluster Configuration


```bash
kubectl create secret generic aws-credentials \
  --from-literal=aws-access-key=YOUR_AWS_ACCESS_KEY_ID \
  --from-literal=aws-secret-key=YOUR_AWS_SECRET_ACCESS_KEY \
  -n code-analyzer
```

```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
```

```bash
kubectl apply -f https://raw.githubusercontent.com/argoproj-labs/argocd-image-updater/stable/manifests/install.yaml
```

```bash
kubectl apply -f https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml
```

```bash
kubectl -n kube-system patch deploy metrics-server \
  --type='json' \
  -p='[{"op": "add", "path": "/spec/template/spec/containers/0/args/-", "value":"--kubelet-insecure-tls"},
       {"op": "add", "path": "/spec/template/spec/containers/0/args/-", "value":"--kubelet-preferred-address-types=InternalIP"}]'
```

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/cloud/deploy.yaml
```

```bash
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 -d
```