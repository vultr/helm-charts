# Helm Charts for Vultr

Helm Charts for Vultr.

# Requirements

You will [need helm installed](https://v3.helm.sh/docs/intro/install/) in order to use these with your Kubernetes cluster.

The `vultr-ccm` and `vultr-csi` packet require `Secret` on your cluster prior the deploment of either helm chart. This secret contains your Vultr API key which allows the CCM and CSI to configure resources on your account.

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: vultr-helm-secret
  namespace: kube-system
stringData:
  # Replace the api-key with proper values
  api-key: "VULTR_API_KEY"
    # Region is no longer needed as of v0.0.3
    # region: "VULTR_REGION"
```

# Charts

Each helm chart resides within it's own directory. Here are the current available charts.

## vultr-ccm
The vultr-ccm is the [Cloud Controller Manager](https://github.com/vultr/vultr-csi) for Vultr.

`helm install --generate-name --debug ./vultr-ccm`

## vultr-csi
The vultr-csi is the [Container Storage Interface](https://github.com/vultr/vultr-cloud-controller-manager) for Vultr.

`helm install --generate-name --debug ./vultr-csi`
