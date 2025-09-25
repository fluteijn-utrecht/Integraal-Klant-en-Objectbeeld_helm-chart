# iko

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 0.1.0](https://img.shields.io/badge/AppVersion-0.1.0-informational?style=flat-square)

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
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| livenessProbe.failureThreshold | int | `3` |  |
| livenessProbe.httpGet.path | string | `"/actuator/health"` |  |
| livenessProbe.httpGet.port | string | `"admin-port"` |  |
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
| ports[0].name | string | `"admin-port"` |  |
| readinessProbe.failureThreshold | int | `3` |  |
| readinessProbe.httpGet.path | string | `"/actuator/health"` |  |
| readinessProbe.httpGet.port | string | `"admin-port"` |  |
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
| settings.iko.connectors.bag.apikey | string | `""` | API-sleutel voor toegang tot BAG Or, if using existingSecret: `IKO_CONNECTORS_BAG_APIKEY` |
| settings.iko.connectors.bag.host | string | `"https://api.bag.kadaster.nl"` | URL van de BAG-bron |
| settings.iko.connectors.bag.specificationuri | string | `""` |  |
| settings.iko.connectors.brp.host | string | `""` | URL van de BRP-bron |
| settings.iko.connectors.brp.secret | string | `""` | Geheim/token voor toegang tot BRP Or, if using existingSecret: `IKO_CONNECTORS_BRP_SECRET` |
| settings.iko.connectors.brp.specificationuri | string | `"https://raw.githubusercontent.com/BRP-API/Haal-Centraal-BRP-bevragen/refs/tags/v2.2.1-mock/specificatie/genereervariant/openapi.json"` |  |
| settings.iko.connectors.objects.host | string | `""` | URL van de Objects-bron |
| settings.iko.connectors.objects.specificationuri | string | `""` | OpenAPI specificatie-URL voor de Objects-bron |
| settings.iko.connectors.objects.token | string | `""` | Token bij de Objects-client Or, if using existingSecret: `IKO_CONNECTORS_OBJECTENAPI_TOKEN` |
| settings.iko.connectors.openklant.host | string | `""` | URL van de Open Klant-bron |
| settings.iko.connectors.openklant.specificationuri | string | `""` | OpenAPI specificatie-URL voor de Open Klant-bron |
| settings.iko.connectors.openklant.token | string | `""` | Token voor authenticatie bij de Open Klant-bron Or, if using existingSecret: `IKO_CONNECTORS_OPENKLANT_TOKEN` |
| settings.iko.connectors.openzaak.clientId | string | `""` | Client-ID voor Open Zaak-authenticatie |
| settings.iko.connectors.openzaak.host | string | `""` | URL van Open Zaak-bron |
| settings.iko.connectors.openzaak.secret | string | `""` | Secret bij de Open Zaak-client Or, if using existingSecret: `IKO_CONNECTORS_OPENZAAK_SECRET` |
| settings.iko.connectors.openzaak.specificationuri | string | `""` |  |
| settings.iko.serverPort | int | `8080` | Port IKO listens on |
| settings.keycloak.authServerURL | string | `""` | URL of Keycloak - Required |
| settings.keycloak.clientID | string | `""` | Client-ID to connect with Keycloak |
| settings.keycloak.clientSecret | string | `""` | Client-Secret to connect with Keycloak. Or, if using existingSecret: `KEYCLOAK_CREDENTIALS_SECRET` and `SPRING_SECURITY_OAUTH2_CLIENT_REGISTRATION_KEYCLOAKAPI_CLIENTSECRET` (must set both) |
| settings.keycloak.publicKey | string | `""` | Keycloak's Public Key used to verify signature of JWTs - Required. In Keycloak, this can be found under (in the realm you're using): 'Realm settings' -> 'Keys'.  Use the public key with Use: 'SIG' and Provider: 'rsa-generated'. |
| settings.keycloak.realm | string | `""` | Keycloak realm - Required |
| settings.management.endpoint.health.enabled | bool | `true` | Enable the Actuator health endpoint |
| settings.management.endpoint.health.probes.enabled | bool | `true` | Enable the Kubernetes probe extensions on the health endpoint |
| settings.management.endpoint.health.showDetails | string | `"when_authorized"` | Show health details when the caller is authorised |
| settings.management.endpoints.web.basePath | string | `"/actuator"` | Base path for Actuator endpoints |
| settings.management.endpoints.web.exposure.include | string | `"health,info,prometheus"` | Comma-separated list of Actuator endpoints to expose |
| settings.spring.actuator.password | string | `"TOPSECRET"` | Password to access the Spring actuator endpoint |
| settings.spring.actuator.username | string | `"admin"` | Username to access the Spring actuator endpoint |
| settings.spring.datasource.driverClassName | string | `"org.postgresql.Driver"` | Driver for the postgresql database |
| settings.spring.datasource.password | string | `"TOPSECRET"` | Password for the postgresql database |
| settings.spring.datasource.url | string | `""` | URL for the postgresql database |
| settings.spring.datasource.username | string | `""` | Username for the postgresql database |
| settings.spring.jpa.properties.hibernateDialect | string | `"org.hibernate.dialect.PostgreSQLDialect"` |  |
| settings.spring.profiles.active | string | `"cloud"` | Activated Spring profiles |
| startupProbe.failureThreshold | int | `30` |  |
| startupProbe.httpGet.path | string | `"/actuator/health"` |  |
| startupProbe.httpGet.port | string | `"admin-port"` |  |
| startupProbe.initialDelaySeconds | int | `5` |  |
| startupProbe.periodSeconds | int | `10` |  |
| tolerations | list | `[]` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
