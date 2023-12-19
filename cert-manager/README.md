# cert-manager-webhook-vultr

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: v0.1.0](https://img.shields.io/badge/AppVersion-v0.1.0-informational?style=flat-square)

A Vultr cert-manager repo for creating an ACME DNS01 solver webhook

**Homepage:** <https://github.com/vultr/cert-manager-webhook-vultr>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| David Dymko |  |  |

## Source Code

* <https://github.com/vultr/cert-manager-webhook-vultr>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| certManager.namespace | string | `"cert-manager"` |  |
| certManager.serviceAccountName | string | `"cert-manager"` |  |
| fullnameOverride | string | `""` |  |
| groupName | string | `"acme.vultr.com"` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"vultr/cert-manager-webhook-vultr"` |  |
| image.tag | string | `"v0.1.0"` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| resources | object | `{}` |  |
| service.port | int | `443` |  |
| service.type | string | `"ClusterIP"` |  |
| tolerations | list | `[]` |  |

