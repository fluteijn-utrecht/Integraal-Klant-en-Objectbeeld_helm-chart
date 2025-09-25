# iko

![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.2.0](https://img.shields.io/badge/AppVersion-0.2.0-informational?style=flat-square)

A Helm chart for Integraal Klant Objectbeeld (IKO)

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` |  |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| autoscaling.targetMemoryUtilizationPercentage | string | `nil` |  |
| existingSecret | string | `nil` |  |
| extraEnvVars | list | `[]` | Extra environment variables to inject into the container |
| extraVolumeMounts | list | `[]` | Additional volume mounts for the main container |
| extraVolumes | list | `[]` | Additional volumes to attach to the pod |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` | Pull policy for the image |
| image.repository | string | `""` | Domain of the image repository |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"iko.example.com"` |  |
| ingress.hosts[0].paths[0].path | string | `"/admin"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[1].path | string | `"/login"` |  |
| ingress.hosts[0].paths[1].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[2].path | string | `"/oauth2"` |  |
| ingress.hosts[0].paths[2].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[3].path | string | `"/endpoints"` |  |
| ingress.hosts[0].paths[3].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[4].path | string | `"/aggregated-data-profiles"` |  |
| ingress.hosts[0].paths[4].pathType | string | `"Prefix"` |  |
| ingress.hosts[0].paths[5].path | string | `"/tab-illo.png"` |  |
| ingress.hosts[0].paths[5].pathType | string | `"Prefix"` |  |
| ingress.tls | list | `[]` |  |
| livenessProbe.failureThreshold | int | `3` |  |
| livenessProbe.httpGet.path | string | `"/login"` |  |
| livenessProbe.httpGet.port | string | `"http"` |  |
| livenessProbe.initialDelaySeconds | int | `10` |  |
| livenessProbe.periodSeconds | int | `30` |  |
| livenessProbe.successThreshold | int | `1` |  |
| livenessProbe.timeoutSeconds | int | `1` |  |
| monitoring.podMonitor.enabled | bool | `false` |  |
| monitoring.podMonitor.interval | string | `""` | Interval between Prometheus scrapes |
| monitoring.podMonitor.scrapeTimeout | string | `""` | Scrape timeout for the PodMonitor |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| persistence.accessModes | list | `["ReadWriteOnce"]` | Access modes for the PVC |
| persistence.annotations | object | `{}` |  |
| persistence.enabled | bool | `false` | Enable/disable persistent volumes for iko |
| persistence.existingClaim | string | `nil` | persistence.existingClaim The name of an existing PVC to use for persistence |
| persistence.extraPvcLabels | object | `{}` | Extra labels to add to the PVC metadata |
| persistence.finalizers | list | `[]` | Finalizers to add to the PVC |
| persistence.mountPath | string | `"/tmp"` | persistence.mountPath Path to mount the volume at. |
| persistence.selectorLabels | object | `{}` | Additional selector labels for the PVC |
| persistence.size | string | `"1Gi"` | persistence.size Size of data volume |
| persistence.storageClassName | string | `""` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext.fsGroup | int | `1000` |  |
| ports[0].containerPort | int | `8080` |  |
| ports[0].name | string | `"http"` |  |
| readinessProbe.failureThreshold | int | `3` |  |
| readinessProbe.httpGet.path | string | `"/login"` |  |
| readinessProbe.httpGet.port | string | `"http"` |  |
| readinessProbe.periodSeconds | int | `10` |  |
| readinessProbe.successThreshold | int | `1` |  |
| readinessProbe.timeoutSeconds | int | `1` |  |
| replicaCount | int | `1` | Amount of replicas running IKO |
| resources | object | `{}` |  |
| securityContext.capabilities.drop[0] | string | `"ALL"` |  |
| securityContext.readOnlyRootFilesystem | bool | `false` |  |
| securityContext.runAsNonRoot | bool | `true` |  |
| securityContext.runAsUser | int | `1000` |  |
| service.management | bool | `false` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | If not set and create is true, a name is generated using the fullname template |
| settings.iko.connectors.bag.apikey | string | `""` | API key for accessing BAG Or, if using existingSecret: `IKO_CONNECTORS_BAG_APIKEY` |
| settings.iko.connectors.bag.enabled | bool | `false` | Enable the BAG connector |
| settings.iko.connectors.bag.host | string | `"https://api.bag.kadaster.nl"` | URL of the BAG service |
| settings.iko.connectors.bag.specificationuri | string | `""` | BAG specification URL |
| settings.iko.connectors.brp.enabled | bool | `false` | Enable the BRP connector |
| settings.iko.connectors.brp.host | string | `""` | URL of the BRP service |
| settings.iko.connectors.brp.secret | string | `""` | Secret/token for accessing BRP Or, if using existingSecret: `IKO_CONNECTORS_BRP_SECRET` |
| settings.iko.connectors.brp.specificationuri | string | `"https://raw.githubusercontent.com/BRP-API/Haal-Centraal-BRP-bevragen/refs/tags/v2.2.1-mock/specificatie/genereervariant/openapi.json"` |  |
| settings.iko.connectors.objects.enabled | bool | `false` | Enable the Objects connector |
| settings.iko.connectors.objects.host | string | `""` | URL of the Objects service |
| settings.iko.connectors.objects.specificationuri | string | `""` | OpenAPI specification URL for the Objects service |
| settings.iko.connectors.objects.token | string | `""` | Token for the Objects client Or, if using existingSecret: `IKO_CONNECTORS_OBJECTENAPI_TOKEN` |
| settings.iko.connectors.openklant.enabled | bool | `false` | Enable the Open Klant connector |
| settings.iko.connectors.openklant.host | string | `""` | URL of the Open Klant service |
| settings.iko.connectors.openklant.specificationuri | string | `""` | OpenAPI specification URL for the Open Klant service |
| settings.iko.connectors.openklant.token | string | `""` | Token used to authenticate with the Open Klant service Or, if using existingSecret: `IKO_CONNECTORS_OPENKLANT_TOKEN` |
| settings.iko.connectors.openzaak.clientId | string | `""` | Client ID used to authenticate with Open Zaak |
| settings.iko.connectors.openzaak.enabled | bool | `false` | Enable the Open Zaak connector |
| settings.iko.connectors.openzaak.host | string | `""` | URL of the Open Zaak service |
| settings.iko.connectors.openzaak.secret | string | `""` | Secret for the Open Zaak client Or, if using existingSecret: `IKO_CONNECTORS_OPENZAAK_SECRET` |
| settings.iko.connectors.openzaak.specificationuri | string | `""` | OpenZaak specification URL |
| settings.iko.serverPort | int | `8080` | Port IKO listens on |
| settings.keycloak.authServerURL | string | `""` | URL of Keycloak - Required |
| settings.keycloak.clientID | string | `""` | Client-ID to connect with Keycloak |
| settings.keycloak.clientSecret | string | `""` | Client-Secret to connect with Keycloak. Or, if using existingSecret: `KEYCLOAK_CREDENTIALS_SECRET` and `SPRING_SECURITY_OAUTH2_CLIENT_REGISTRATION_KEYCLOAKAPI_CLIENTSECRET` (must set both) |
| settings.keycloak.publicKey | string | `""` | Use the public key with Use: 'SIG' and Provider: 'rsa-generated'. |
| settings.keycloak.realm | string | `""` | Keycloak realm - Required |
| settings.spring.actuator.password | string | `"TOPSECRET"` | Password to access the Spring actuator endpoint |
| settings.spring.actuator.username | string | `"admin"` | Username to access the Spring actuator endpoint |
| settings.spring.datasource.driverClassName | string | `"org.postgresql.Driver"` | Driver for the postgresql database |
| settings.spring.datasource.password | string | `"TOPSECRET"` | Password for the postgresql database |
| settings.spring.datasource.url | string | `""` | URL for the postgresql database |
| settings.spring.datasource.username | string | `""` | Username for the postgresql database |
| settings.spring.jpa.properties.hibernateDialect | string | `"org.hibernate.dialect.PostgreSQLDialect"` |  |
| settings.spring.profiles.active | string | `"cloud"` | Activated Spring profiles |
| startupProbe.failureThreshold | int | `30` |  |
| startupProbe.httpGet.path | string | `"/login"` |  |
| startupProbe.httpGet.port | string | `"http"` |  |
| startupProbe.initialDelaySeconds | int | `5` |  |
| startupProbe.periodSeconds | int | `10` |  |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
