# Vultr-csi

The `vultr-csi` requires a `Secret` on your cluster prior the deploment of either helm chart. This secret contains your Vultr API key which allows the csi to configure resources on your account.

```yaml
apiVersion: v1
kind: Secret
metadata:
  name: vultr-helm-secret
  namespace: kube-system
stringData:
  # Replace the api-key with proper values
  api-key: "VULTR_API_KEY"
```