# dd-manager
DD-Manager was designed to simplify datadog monitor administration. This is an operator that emits datadog monitors based on kubernetes state. The operator responds to changes of resources in your kubernetes cluster and will manage datadog monitors based on the configured state.

More information about dd-manager is available on [GitHub](https://github.com/reactiveops/dd-manager).

## Installation
We recommend installing dd-manager in it's own namespace and with a simple release name:

```
helm install incubator/dd-manager --name dd-manager --namespace dd-manager
```

## Prerequisites
Kubernetes 1.11+, Helm 2.13+

## Configuration
Parameter | Description | Default
--- | --- | ---
`image.repository` | Docker image repo  | `quay.io/reactiveops/dd-manager`
`image.tag` | Docker image tag  | `dev-0.1.1`
`image.pullPolicy` | Docker image pull policy  | `IfNotPresent`
`resources.requests.cpu` | CPU resource request | `100m`
`resources.requests.memory` | Memory resource request | `128Mi`
`resources.limits.cpu` | CPU resource limit | `100m`
`resources.limits.memory` | Memory resource limit | `128Mi`
`nodeSelector` | Deployment nodeSelector | `{}`
`tolerations` | Deployment tolerations | `[]`
`affinity` | Deployment affinity | `{}`
`datadog.apiKey` | Datadog api key | `""`
`datadog.appKey` | Datadog app key | `""`
`definitionsPath` | The path to the monitor definitions configuration. This can be a local path or a URL. | `""`
`owner` | A unique name to designate as the owner. This will be applied as a tag to identified managed monitors. | `dd-manager`
`DryRun` | when set to true monitors will not be managed in datadog. | `false`