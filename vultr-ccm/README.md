# Vultr-ccm

The Vultr Cloud Controller Manager (ccm) provides a fully supported experience of Vultr features in your Kubernetes cluster.

- Node resources are assigned their respective Vultr instance hostnames, Region, PlanID and public/private IPs.
- Node resources get put into their proper state if they are shutdown or removed. This allows for Kubernetes to properly reschedule pods
- Vultr LoadBalancers are automatically deployed when a LoadBalancer service is deployed.


## Prerequisites

- Helm v3+ is required to install the `ccm` charts

## Installation

### Get Repo Info

```
helm repo add vultr https://vultr.github.io/helm-charts
helm repo update
```

See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation.

### Installing the Chart

First, you will need to deploy a secret with your api key. 

```shell
kubectl create secret generic "vultr-helm-secret" --from-literal=api-key=<VULTR API KEY> --namespace=kube-system
```

Second, you will deploy the helm chart.

```shell
# Helm
helm install [RELEASE_NAME] vultr/vultr-ccm
```

This will deploy all necessary services, deployments, rbac, and various other resources required for cert-manager.

### Uninstall the Chart
To uninstall the webhook run the following:

```shell
# Helm
helm uninstall [RELEASE_NAME]
```
See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation.
