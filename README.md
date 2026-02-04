# DMSS Helm Charts

This repository contains Helm charts for:
- dmss-archive-services
- dmss-archive-services-fallback
- container-signature-service

## Quick start
```bash
helm install dmss-archive-services ./dmss-archive-services --namespace dmss --create-namespace
helm install dmss-archive-services-fallback ./dmss-archive-services-fallback --namespace dmss
helm install container-signature-service ./container-signature-service --namespace dmss
```

Each chart includes a README with configuration details and defaults.
