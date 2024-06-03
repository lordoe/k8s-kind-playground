# Stateful Set

## Headless Service

A headless service is a service with the `clusterIP: None` field in the service spec. This means that the service is not load balanced and does not have a stable IP address. Instead, the DNS server returns multiple A records for the service's name, each pointing to the IP of an individual pod. This is useful for stateful applications that require stable network identifiers.

To create a headless service and a stateful set with 3 replicas, run the following command:

