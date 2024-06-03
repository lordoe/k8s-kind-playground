# Demo of using storage (pv, pvc, storage class) in k8s

the default storage class in KIND is rancher.io/local-path
```bash
kubectl get storageclass
```
NAME                 PROVISIONER             RECLAIMPOLICY   VOLUMEBINDINGMODE      ALLOWVOLUMEEXPANSION   AGE
standard (default)   rancher.io/local-path   Delete          WaitForFirstConsumer   false                  3h6m

## create a persistent volume claim
```bash
kubectl apply -f pvc.yaml -n playground
```

this uses the storage class rancher.io/local-path and create a persistent volume when the first consumer is created

## create a pod with the persistent volume claim
```bash
kubectl apply -f pod.yaml -n playground
```

describe the pv
```bash
kubectl get pv
kubectl describe pv <pv-name>
```

this will show the path of the volume on the host machine
```yaml
<snip>
Source:
    Type:          HostPath (bare host directory volume)
    Path:          /var/local-path-provisioner/pvc-bbc95502-0a28-4d21-baf5-ecfe747601f4_playground_my-pvc
```

so the volume is created at given path on the node where the pod is running

the volume is deleted when the pod is deleted and the pvc is deleted