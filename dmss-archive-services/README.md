# dmss-archive-services Helm Chart

This chart deploys the DMSS Archive Services application and its related configuration files.

## Requirements
- Kubernetes 1.19+
- Helm 3.8+

## Install
```bash
helm install dmss-archive-services ./dmss-archive-services \
  --namespace dmss --create-namespace
```

## Configuration
Update these values before deploying to a client environment:
- `image.repository`, `image.tag`
- `config.applicationYaml` (database credentials, service endpoints)
- `ingress.*` (hostnames, TLS)
- `env.JAVA_OPTS`
 - `fullnameOverride` (defaults to `avafin-archive-services`)

The chart mounts three config files into the container:
- `application.yml`
- `metaForDoc.json`
- `metaspec.json`

## Notes
- Defaults are taken from repo config and include demo placeholders.
- If you need HPA, set `hpa.enabled=true`.

## Example override
```bash
helm upgrade --install dmss-archive-services ./dmss-archive-services \
  --namespace dmss \
  --set image.tag=1.2.3 \
  --set ingress.enabled=true
```
