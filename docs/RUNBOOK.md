# Runbook

## Service

- Name: `ledger-api`
- Team: `Commerce`
- Owner: `mooref068@gmail.com`
- Cost center: `commerce`

## First Checks

```bash
kubectl get rollout ledger-api -n ledger-api-dev
kubectl get pods -l app.kubernetes.io/name=ledger-api -n ledger-api-dev
kubectl logs -l app.kubernetes.io/name=ledger-api -n ledger-api-dev
```

## Health

```bash
curl https://ledger-api.dev.platform.ohanyere.internal/healthz
curl https://ledger-api.dev.platform.ohanyere.internal/readyz
curl https://ledger-api.dev.platform.ohanyere.internal/livez
```

## Rollback

```bash
kubectl argo rollouts undo ledger-api -n ledger-api-dev
```

Escalate to `Commerce` through `mooref068@gmail.com` if rollback does not restore service.
