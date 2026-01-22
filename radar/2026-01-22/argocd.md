---
title:      "ArgoCD"
ring:       adopt
quadrant:   tools
tags:       [gitops, cd, kubernetes, continuous-delivery, deployment]
---

## Varför ADOPT?

ArgoCD är den ledande GitOps continuous delivery-lösningen för Kubernetes. Deklarativ, Git-driven deployment med kraftfull UI, robust sync, och production-proven hos tusentals organisationer. Perfekt komplement till GitOps-metodiken.

**Core strengths:**
- **GitOps-native** - Git som single source of truth
- **Kubernetes-fokuserad** - Djup integration med K8s
- **Robust UI** - Excellent visibility och troubleshooting
- **Multi-cluster** - Manage många clusters från en instans
- **Automated sync** - Continuous reconciliation mellan Git och cluster
- **CNCF graduated** - Production-ready och community-backed

## Key features

**Application deployment:**
- Deklarativa Kubernetes manifests (YAML)
- Helm charts
- Kustomize
- Jsonnet
- Custom config management tools

**Sync strategies:**
- **Automated sync** - Continuous deployment vid Git-ändringar
- **Manual sync** - Approval-based deployment
- **Sync waves** - Ordered deployment av resources
- **Sync hooks** - Pre/post-sync jobs

**Multi-tenancy:**
- Projects för team isolation
- RBAC integration (SSO, LDAP, OIDC)
- AppProjects för policy enforcement

## Architecture

**Core components:**
- **API Server** - gRPC/REST API
- **Repository Server** - Git repository checkout och manifest generation
- **Application Controller** - Reconciliation loop
- **UI/CLI** - User interfaces

**Deployment pattern:**
```
Git Repository → ArgoCD → Kubernetes Cluster(s)
```

## Best practices

**Repository structure:**
```
gitops-repo/
├── applications/          # ArgoCD Application definitions
├── base/                  # Base Kubernetes manifests
├── overlays/
│   ├── dev/
│   ├── staging/
│   └── prod/
└── helm-values/           # Helm value files per environment
```

**Application definitions:**
- App-of-apps pattern för många applications
- ApplicationSets för dynamic application generation
- Separate repos för app code vs GitOps config

**Sync policies:**
- Automated sync för non-prod
- Manual sync + approval för prod
- Self-heal för auto-recovery från drift
- Prune för att ta bort orphaned resources

**Security:**
- Private repos via SSH keys eller tokens
- Secrets management integration (Sealed Secrets, External Secrets Operator)
- RBAC för team access control
- Image updater för automated container updates

**Health checks:**
- Custom health assessments
- Resource hooks för migrations
- Sync waves för ordered rollout

## Multi-cluster management

**Patterns:**
- **Hub-spoke** - En ArgoCD instance, många target clusters
- **Standalone** - ArgoCD per cluster
- **Hybrid** - Combination baserat på team/environment

**Cluster registration:**
```bash
argocd cluster add <context-name>
```

## Integration med CI

**Separation of concerns:**
- **CI** (GitHub Actions, GitLab CI, Jenkins) - Build, test, push image
- **CD** (ArgoCD) - Deploy till Kubernetes

**Image update strategies:**
1. CI uppdaterar Git manifest med ny image tag
2. ArgoCD Image Updater (automated)
3. Renovate/Dependabot för dependency updates

## ArgoCD vs alternativ

**ArgoCD vs Flux:**
- ArgoCD: Better UI, multi-cluster management
- Flux: More GitOps-purist, lightweight, Helm-native
- Båda: CNCF graduated, production-ready

**ArgoCD vs Jenkins:**
- ArgoCD: GitOps-native, declarative, Kubernetes-fokus
- Jenkins: General CI/CD, imperative, broader use cases

**ArgoCD vs Spinnaker:**
- ArgoCD: Enklare, Kubernetes-native, GitOps
- Spinnaker: Multi-cloud, more complex, enterprise features

## Installation

**Quick start:**
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

**Production:**
- High availability mode (multiple replicas)
- Redis clustering
- Ingress med TLS
- SSO integration
- Metrics export (Prometheus)

## Monitoring & Observability

**Metrics:**
- Prometheus metrics export
- Grafana dashboards
- Application health status
- Sync status och drift detection

**Notifications:**
- Slack, Teams, email integrations
- Webhook notifications
- Custom triggers på events

## Utmaningar

⚠️ **Tänk på:**
- Lärande kurva för GitOps-tänk
- Secrets management kräver extra tooling
- Large-scale (1000+ apps) kan kräva tuning
- RBAC kan bli komplext för stora teams
- Sync performance för very large manifests

## Adoption strategy

**Phase 1 - Pilot:**
1. Installera ArgoCD i dev cluster
2. Onboarda 2-3 pilot applications
3. Etablera Git repository structure
4. Team training på GitOps workflow

**Phase 2 - Expansion:**
1. Rulla ut till fler dev/staging apps
2. Implementera secrets management
3. Sätt upp multi-cluster management
4. Integrera med CI pipelines

**Phase 3 - Production:**
1. Production deployments med approval flows
2. Disaster recovery procedures
3. Monitoring och alerting
4. Team self-service via AppProjects

## Further reading

- [ArgoCD Documentation](https://argo-cd.readthedocs.io/)
- [ArgoCD Best Practices](https://argo-cd.readthedocs.io/en/stable/user-guide/best_practices/)
- [GitOps with ArgoCD (book)](https://www.manning.com/books/gitops-and-kubernetes)
- [CNCF ArgoCD Project](https://www.cncf.io/projects/argo/)
