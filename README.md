# K8S kind playground

This repository contains instructions for setting up a kubernetes playground using kind (kubernetes in Docker). It contains various k8s manifests for pacticing deployment of different kubernetes resources and sample applications.

The kubernetes cluster is created using kind (Kubernetes in Docker) and some resources are kind specific (e.g. ingress controller).

## Applications

- Ingress Nginx Controller
- ArgoCD
- Wordpress

In order for some applications to work, you need to have a storage class in your kubernetes cluster.

The Ingress Controller should be installed first before deploying other applications in order to have a working ingress.

## Prerequisites

- [kind](https://kind.sigs.k8s.io/docs/user/quick-start/)
- [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/)
- [helm](https://helm.sh/docs/intro/install/) (optional)

## Getting Started

1. Create a kubernetes cluster using kind

```bash
kind create cluster --config kind-config.yaml
```

2. Play around with the different applications and resources