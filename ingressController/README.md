# Nginx Ingress Controller

## Installation via Helm

add repo
```bash
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
```

pull helm chart
```bash
helm pull ingress-nginx/ingress-nginx --untar
```

install helm chart
```bash
helm install ingress-nginx ingress-nginx
```

## installation for KIND cluster

```bash
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

or curl the file and apply
```bash
curl -O https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
kubectl apply -f deploy.yaml
```