# FORK OF core/consul - THIS EXISTS ONLY TO PUBLISH qbrd/consul docker image.

# Habitat package: consul

## Description

[Consul](1) is Service Discovery and Configuration Made Easy.

This plan provides the static binary for execution.

## Usage

```
hab svc load core/consul
```

## Topology

Consul can be deployed as a single node for testing, with `standalone` topology, or in a multi-node setup also as `standalone`. The nodes share the same configuration, and can utilize service member IP addresses for [consul join commands](2) or using the [start_join configuration](2) options.

## Update Strategy

Recommended update strategy for Consul is `rolling`.

## Usage with K8s

```
# Apply RBAC Rules for habitat operator
kubectl apply -f https://raw.githubusercontent.com/habitat-sh/habitat-operator/master/examples/rbac/rbac.yml

# Deploy the Habitat Operator
kubectl apply -f https://raw.githubusercontent.com/habitat-sh/habitat-operator/master/examples/rbac/habitat-operator.yml

# Deploy Consul:
kubectl apply -f https://raw.githubusercontent.com/qubitrenegade/habitat-consul/master/examples/consul-k8s.yaml

# You should see three nodes up and running!
kubectl get pods
```

[1]: https://consul.io
[2]: https://www.consul.io/docs/guides/bootstrapping.html
