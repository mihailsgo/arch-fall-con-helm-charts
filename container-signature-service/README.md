# container-signature-service Helm Chart

This chart deploys DMSS Container and Signature Services with optional Hazelcast headless service and ingress.

## Requirements
- Kubernetes 1.19+
- Helm 3.8+

## Install
```bash
helm install container-signature-service ./container-signature-service \
  --namespace dmss --create-namespace
```

## Configuration
Update before deploying:
- `image.repository`, `image.tag`
- `config.applicationYaml` (service URLs, Smart-ID credentials)
- `env.HAZELCAST_KUBERNETES_SERVICE_DNS` if you change the headless service name
- `ingress.*`

## Smart-ID Only
The default config includes multiple signing providers from the repo. If the client only uses Smart-ID, remove or disable other provider blocks inside `config.applicationYaml` to avoid accidental enablement.

## Notes
- If you do not need Hazelcast headless service, set `headlessService.enabled=false`.
- If you want a LoadBalancer service, set `loadBalancer.enabled=true`.

## Example override
```bash
helm upgrade --install container-signature-service ./container-signature-service \
  --namespace dmss \
  --set image.tag=1.0.6 \
  --set ingress.enabled=true
```
