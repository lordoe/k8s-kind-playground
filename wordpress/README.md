# Wordpress

You can either install wordpress manually using the manifests in `manual` directory or use the helm chart in `helm` directory.

## Prerequisites

- storage class

## 1. Manual Installation

This would create some resources in the wordpress namespace

- statefulset for mysql
- deployment for wordpress
- service for wordpress
- service for mysql
- secret for mysql root password
- pv and pvc for mysql data (through template in the statefulset manifest)
- pv and pvc for wordpress data

```bash
kubectl apply -f manual/ -n wordpress
```

## 2. Helm Installation

This would install wordpress and mysql using the helm chart

```bash
helm install wordpress oci://registry-1.docker.io/bitnamicharts/wordpress -n wordpress
```