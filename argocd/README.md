# deploy argocd on kind cluster using helm

add repo and pull helm chart to explore it (optional)

```bash
helm repo add argo https://argoproj.github.io/argo-helm
helm pull argo/argo-cd --untar
```

## important for ingress

adjust the insecure flag to true in values.yaml
```yaml
server.insecure: true
```

this is important because otherwise argocd would redirect to https but the ingress controller already terminated the ssl connection

or through the command line
```bash
helm install argocd argo/argo-cd --namespace argocd --set server.insecure=true
```

install argocd
```bash
helm install argocd argo/argo-cd --namespace argocd
```

## configure the ingress

```bash
kubectl apply -f ingress.yaml -n argocd
```