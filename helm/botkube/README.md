# BotKube

![Version: v0.12.3](https://img.shields.io/badge/Version-v0.12.3-informational?style=flat-square) ![AppVersion: v0.12.3](https://img.shields.io/badge/AppVersion-v0.12.3-informational?style=flat-square)

Controller for the BotKube Slack app which helps you monitor your Kubernetes cluster, debug deployments and run specific checks on resources in the cluster.

**Homepage:** <https://www.botkube.io>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| PrasadG193 | prasad.ghangal@gmail.com |  |
| ssudake21 | sanket@infracloud.io |  |

## Source Code

* <https://github.com/infracloudio/botkube>

### Now Supports AWS IRSA on EKS

AWS has introduced IAM Role for Service Accounts in order to provide fine grained access. This is useful if you are looking to run BotKube inside an EKS cluster. For more details visit https://docs.aws.amazon.com/eks/latest/userguide/iam-roles-for-service-accounts.html.

Annotate the BotKube Service Account as shown in the example below and add the necessary Trust Relationship to the corresponding BotKube role to get this working

```
serviceAccount:
  annotations:
    eks.amazonaws.com/role-arn: "<role_arn_to_assume>"
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| communications.discord.botid | string | `"DISCORD_BOT_ID"` |  |
| communications.discord.channel | string | `"DISCORD_CHANNEL_ID"` |  |
| communications.discord.enabled | bool | `false` |  |
| communications.discord.notiftype | string | `"short"` |  |
| communications.discord.token | string | `"DISCORD_TOKEN"` |  |
| communications.elasticsearch.awsSigning.awsRegion | string | `"us-east-1"` |  |
| communications.elasticsearch.awsSigning.enabled | bool | `false` |  |
| communications.elasticsearch.awsSigning.roleArn | string | `""` |  |
| communications.elasticsearch.enabled | bool | `false` |  |
| communications.elasticsearch.index.name | string | `"botkube"` |  |
| communications.elasticsearch.index.replicas | int | `0` |  |
| communications.elasticsearch.index.shards | int | `1` |  |
| communications.elasticsearch.index.type | string | `"botkube-event"` |  |
| communications.elasticsearch.password | string | `"ELASTICSEARCH_PASSWORD"` |  |
| communications.elasticsearch.server | string | `"ELASTICSEARCH_ADDRESS"` |  |
| communications.elasticsearch.skipTLSVerify | bool | `false` |  |
| communications.elasticsearch.username | string | `"ELASTICSEARCH_USERNAME"` |  |
| communications.existingSecretName | string | `""` |  |
| communications.mattermost.botName | string | `"BotKube"` |  |
| communications.mattermost.channel | string | `"MATTERMOST_CHANNEL"` |  |
| communications.mattermost.enabled | bool | `false` |  |
| communications.mattermost.notiftype | string | `"short"` |  |
| communications.mattermost.team | string | `"MATTERMOST_TEAM"` |  |
| communications.mattermost.token | string | `"MATTERMOST_TOKEN"` |  |
| communications.mattermost.url | string | `"MATTERMOST_SERVER_URL"` |  |
| communications.slack.channel | string | `"SLACK_CHANNEL"` |  |
| communications.slack.enabled | bool | `false` |  |
| communications.slack.notiftype | string | `"short"` |  |
| communications.slack.token | string | `"SLACK_API_TOKEN"` |  |
| communications.teams.appID | string | `"APPLICATION_ID"` |  |
| communications.teams.appPassword | string | `"APPLICATION_PASSWORD"` |  |
| communications.teams.enabled | bool | `false` |  |
| communications.teams.notiftype | string | `"short"` |  |
| communications.teams.port | int | `3978` |  |
| communications.webhook.enabled | bool | `false` |  |
| communications.webhook.url | string | `"WEBHOOK_URL"` |  |
| config.recommendations | bool | `true` |  about the best practices for the created resource |
| config.resources | list | [] | |
| config.settings.clustername | string | `"not-configured"` |  |
| config.settings.configwatcher | bool | `true` |  |
| config.settings.kubectl.commands.resources | list | [] |  |
| config.settings.kubectl.commands.verbs | list | [] |  |
| config.settings.kubectl.defaultNamespace | string | `"default"` |  |
| config.settings.kubectl.enabled | bool | `false` |  |
| config.settings.kubectl.restrictAccess | bool | `false` |  |
| config.settings.upgradeNotifier | bool | `true` |  |
| config.ssl.enabled | bool | `false` |  |
| containerSecurityContext.allowPrivilegeEscalation | bool | `false` |  |
| containerSecurityContext.privileged | bool | `false` |  |
| containerSecurityContext.readOnlyRootFilesystem | bool | `true` |  |
| extraAnnotations | object | `{}` |  |
| extraEnv | string | `nil` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.registry | string | `"ghcr.io"` |  |
| image.repository | string | `"infracloudio/botkube"` |  |
| image.tag | string | `"v0.12.3"` |  |
| ingress.annotations."kubernetes.io/ingress.class" | string | `"nginx"` |  |
| ingress.create | bool | `false` |  |
| ingress.host | string | `"HOST"` |  |
| ingress.tls.enabled | bool | `false` |  |
| ingress.tls.secretName | string | `""` |  |
| ingress.urlPath | string | `"/"` |  |
| logLevel | string | `"info"` |  |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` |  |
| podSecurityPolicy.enabled | bool | `false` |  |
| priorityClassName | string | `""` |  |
| rbac.create | bool | `true` |  |
| rbac.rules | list | [] |  |
| replicaCount | int | `1` |  |
| resources | object | `{}` |  |
| securityContext | object | `{"runAsGroup":101,"runAsUser":101}` |  set to run as a Non-Privileged user by default |
| service.name | string | `"metrics"` |  |
| service.port | int | `2112` |  |
| service.targetPort | int | `2112` |  |
| serviceAccount.annotations | object | `{}` |  If not set and create is true, a name is generated using the fullname template annotations for the service account |
| serviceAccount.create | bool | `true` |  |
| serviceMonitor.enabled | bool | `false` |  |
| serviceMonitor.interval | string | `"10s"` |  |
| serviceMonitor.labels | object | `{}` |  |
| serviceMonitor.path | string | `"/metrics"` |  |
| serviceMonitor.port | string | `"metrics"` |  |
| tolerations | list | `[]` |  |
