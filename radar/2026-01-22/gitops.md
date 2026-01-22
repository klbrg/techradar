---
title:      "GitOps"
ring:       adopt
quadrant:   methods-and-patterns
tags:       [devops, automation, kubernetes, ci/cd, infrastructure]
---

"GitOps is the best thing since configuration as code. Git changed how we collaborate, but declarative configuration is the key to dealing with infrastructure at scale, and sets the stage for the next generation of management tools"

*\- Kelsey Hightower, Staff Developer Advocate, Google.*

## Varför ADOPT?

GitOps har blivit industry standard för modern cloud-native infrastructure management, särskilt i Kubernetes-miljöer. Det är inte längre en emerging practice utan en provad, produktionsredo metod som har adopterats av organisationer världen över.

**Core benefits:**
- **Declarative everything** - All infrastruktur och konfiguation som kod
- **Git-driven** - Pull requests för ändringar, full historik och rollback-möjligheter  
- **Automated sync** - Continuous reconciliation mellan desired state (Git) och actual state (kluster)
- **Security & compliance** - Built-in audit trail (vem gjorde vad), access control via Git, reduced manual access till production

## Best practices

**Repo-struktur:**
- Separera application code från infrastructure/config repos
- Använd environment branches eller folders (dev/staging/prod)
- Tydlig naming och struktur för skalbarhet

**Verktyg:**
- **Argo CD** - Branschledande för Kubernetes, robust UI och multi-cluster support
- **Flux** - CNCF-projekt, tight Kubernetes integration
  
**Implementation:**
- Börja smått, migrera en app eller ett namespace först
- Etablera clear workflows för configuration changes
- Implementera automated testing för configs (policy-as-code)
- Använd secrets management solutions (sealed secrets, external secrets operator)

## Use cases

- **Kubernetes deployments** - Manifests, Helm charts, Kustomize
- **Infrastructure provisioning** - Terraform modules via GitOps workflow  
- **Multi-cluster management** - Consistent deployments till olika environments
- **Disaster recovery** - Snabb återställning från Git state

## Utmaningar

- Kräver cultural shift - teams behöver embracea Git workflows
- Secret management behöver extra fokus
- Initial setup kan vara komplex för legacy systems
- Monitoring och observability är kritiskt för reconciliation loops

## Further reading

- [GitOps Working Group](https://opengitops.dev/)
