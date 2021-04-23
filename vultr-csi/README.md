# Vultr-ccm

The Container Storage Interface ([CSI](https://github.com/container-storage-interface/spec)) Driver for Vultr [Block Storage](https://www.vultr.com/products/block-storage/). This driver allows you to use Vultr Block Storage with your container orchestrator. We have tested this CSI on Kubernetes.

More information about the CSI and Kubernetes can be found: [CSI Spec](https://github.com/container-storage-interface/spec) and [Kubernetes CSI](https://kubernetes-csi.github.io/docs/example.html)


## Prerequisites

- Helm v3+ is required to install the `vultr-csi` charts

## Installation

### Get Repo Info

```
helm repo add vultr https://vultr.github.io/helm-charts
helm repo update
```

See [helm repo](https://helm.sh/docs/helm/helm_repo/)for command documentation.

### Installing the Chart

First, you will need to deploy a secret with your api key. 

```shell
kubectl create secret generic "vultr-helm-secret" --from-literal=api-key=<VULTR API KEY> --namespace=kube-system
```

Second, you will deploy the helm chart.

```shell
# Helm
helm install [RELEASE_NAME] vultr/vultr-csi
```

This will deploy all necessary services, deployments, rbac, and various other resources required for cert-manager.

### Uninstall the Chart
To uninstall the webhook run the following:

```shell
# Helm
helm uninstall [RELEASE_NAME]
```
See [https://helm.sh/docs/helm/helm_uninstall/](https://helm.sh/docs/helm/helm_uninstall/) for command documentation.
