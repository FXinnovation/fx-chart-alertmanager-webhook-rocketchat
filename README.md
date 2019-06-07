# alertmanager-webhook-rocketchat
## Description
Helm chart for alertmanager-webhook-rocketchat. More information on altermanager-webhook-rocketchat can be found [here]()

## Values
| Key | Default | Description |
| --- | ------- | ----------- |
| replicaCount | `1` | Number of replicas |
| image.repository | `'fxinnovation/awr'` | Repository of the docker image to be used |
| image.tag | `'0.1.0'` | Tag of the docker image to be used |
| image.pullPolicy | `'IfNotPresent'` | Pull policy of the image to be used |
| nameOverride | `''` | overrides the name of the chart |
| fullnameOverride | `''` | overrides the full name of the chart |
| service.type | `'ClusterIP'` | Type of service to be used |
| service.port | `80` | Service port to be used |
| resources.limits.cpu | `100m` | Limit CPU of the container |
| resources.limits.memory | `128Mi` | Memory limit of the container |
| resources.requests.cpu | `10m` | Requested CPU of the container |
| resources.requests.memory | `32Mi` | Memory requested by the container |
| nodeSelector | `{}` | node selection constraint |
| tolerations | `[]` | scheduling tolerations |
| affinity | `{}` | node and inter-pod affinity and ainti-affinity |
| credential_password_secret | `name_secret` | Name of the secret with rocketchat credentials (See example below)
| configuration | see values.yaml | Configuration for the application |

### credential_password_secret
Example Secret Definition
```yaml
---
kind: Secret
apiVersion: v1
metadata:
  name: '<secret name>'
type: Opaque
data:
  email: '<base64 value>'
  name: '<base64 value>'
  password: '<base64 value>'

```
