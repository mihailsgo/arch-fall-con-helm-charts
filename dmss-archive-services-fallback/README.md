# dmss-archive-services-fallback Helm Chart

This chart deploys DMSS Archive Services Fallback with optional persistent storage.

## Requirements
- Kubernetes 1.19+
- Helm 3.8+

## Install
```bash
helm install dmss-archive-services-fallback ./dmss-archive-services-fallback \
  --namespace dmss --create-namespace
```

## Configuration
Update before deploying:
- `image.repository`, `image.tag`
- `config.applicationYaml` (archive service URL, storage mode)
- `persistence.*` if using filesystem storage
- `ingress.*`
 - `fullnameOverride` (defaults to `avafin-archive-services-fallback`)

## Notes
- Defaults are taken from repo config and include local/demo placeholders.
- If you do not want PVCs, set `persistence.enabled=false` (uses `emptyDir`).
- The application config defaults to port 8095; ensure `service.targetPort` matches.

## Example override
```bash
helm upgrade --install dmss-archive-services-fallback ./dmss-archive-services-fallback \
  --namespace dmss \
  --set persistence.size=50Gi
```
