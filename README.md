# FlowMaster K8s Manifests — dev-ben Namespace

Snapshot date: 2026-03-02T00:00:00Z
Source: dev-02 (65.21.52.58), namespace: dev-ben
K3S cluster, all images tagged :ben-dev (frontend-nextjs uses :sso-graceful)

## Deployment Count
58 deployments

## Directory Structure
- `deployments/` — All K8s Deployment manifests
- `services/` — All K8s Service manifests
- `configmaps/` — All ConfigMap manifests
- `pvcs/` — PersistentVolumeClaim manifests
- `ingresses/` — Ingress manifests

## Key Services
- frontend-nextjs (image: dev-ben/frontend-nextjs:sso-graceful) — Real SDX at /dashboard/settings/data-sources
- All backend services at :ben-dev tag

## Restore
To restore this namespace to another cluster:
1. Apply PVCs first: `kubectl apply -f pvcs/ -n TARGET_NAMESPACE`
2. Apply ConfigMaps: `kubectl apply -f configmaps/ -n TARGET_NAMESPACE`
3. Apply Services: `kubectl apply -f services/ -n TARGET_NAMESPACE`
4. Apply Deployments: `kubectl apply -f deployments/ -n TARGET_NAMESPACE`
