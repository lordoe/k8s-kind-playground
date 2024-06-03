# Demo of using services

This directory contains some demo deployments of different services.

## Types of services

- NodePort
- LoadBalancer
- ClusterIP

### NodePort

This would expose the service on a port on each node in the cluster.

### LoadBalancer

This would expose the service using a cloud provider's load balancer.

### ClusterIP

This would expose the service on a cluster-internal IP.

It is accessible only within the cluster and could be accessed using port-forwarding (for testing) or through an ingress controller and ingress resource.