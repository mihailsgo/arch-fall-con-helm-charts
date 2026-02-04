# DMSS Helm Charts

This repository contains Helm charts for:
- dmss-archive-services (defaults to AvaFin resource name)
- dmss-archive-services-fallback (defaults to AvaFin resource name)
- container-signature-service (defaults to AvaFin resource name)

## Quick start
```bash
helm install dmss-archive-services ./dmss-archive-services --namespace dmss --create-namespace
helm install dmss-archive-services-fallback ./dmss-archive-services-fallback --namespace dmss
helm install container-signature-service ./container-signature-service --namespace dmss
```

Each chart includes a README with configuration details and defaults. By default, the charts set `fullnameOverride` to AvaFin-prefixed service names; change it in `values.yaml` if you want different resource names.
