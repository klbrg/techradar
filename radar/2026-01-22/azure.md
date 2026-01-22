---
title:      "Microsoft Azure"
ring:       adopt
quadrant:   platforms-and-operations
tags:       [cloud, azure, microsoft, infrastructure, platforms]
---

## Varför ADOPT?

Azure är den självklara cloud-plattformen för organisationer med befintliga Microsoft-investeringar. Tight integration med Microsoft-ekosystemet (Windows, Active Directory, Office 365, .NET) och stark enterprise focus gör Azure till första valet för många större företag.

**Core strengths:**
- **Microsoft ecosystem** - Seamless integration med AD, Office 365, Dynamics
- **Hybrid cloud** - Bäst-i-klassen hybrid capabilities med Azure Arc och Azure Stack
- **Enterprise ready** - Fokus på compliance, security och governance
- **Regional presence** - Bred geografisk täckning inklusive Sverige (Stockholm region)
- **.NET & Windows** - Förstklassigt stöd för Microsoft development stack

## Key services att kunna

**Compute:**
- **Virtual Machines** - Windows och Linux VMs
- **App Service** - PaaS för web apps och APIs
- **Azure Functions** - Serverless compute
- **AKS** - Azure Kubernetes Service

**Storage & Databases:**
- **Blob Storage** - Object storage (S3-motsvarighet)
- **Azure SQL Database** - Managed SQL Server
- **Cosmos DB** - Globally distributed NoSQL
- **Azure Database for PostgreSQL/MySQL**

**Identity & Security:**
- **Entra ID** - Identity och access management
- **Key Vault** - Secrets management
- **Microsoft Defender for Cloud** - Security posture management

**Observability:**
- **Azure Monitor** - Monitoring och logging
- **Application Insights** - APM och telemetry
- **Log Analytics** - Centralized log management

**Hybrid & Multi-cloud:**
- **Azure Arc** - Manage resources anywhere (on-prem, multi-cloud)
- **Azure Stack** - Run Azure services on-premises

## Best practices

**Landing Zones:**
- Använd Azure Landing Zones för well-architected foundation
- Hub-spoke network topology
- Management groups för hierarkisk governance

**Identity:**
- Entra ID som central identity provider
- Conditional Access policies
- Managed Identities för service-to-service auth

**Governance:**
- Azure Policy för compliance enforcement
- Resource tagging standards
- RBAC (Role-Based Access Control)
- Cost Management + Billing för kostnadskontroll

**Infrastructure as Code:**
- ARM templates eller Bicep (Azure-native)
- Terraform med Azure Verified Modules (AVM) för best practices
- Azure Resource Graph för inventory och queries

## När välja Azure

✅ **Passar bäst för:**
- Enterprise med Microsoft-investeringar (Windows, Office 365, SQL Server)
- Hybrid cloud strategies
- .NET-utveckling och Windows workloads
- Skandinaviska företag (svensk datacenter region)
- Integration med Active Directory krävs

## Utmaningar

⚠️ **Tänk på:**
- Portal UI kan kännas tungrodd jämfört med AWS
- Vissa services saknar paritet med AWS (mindre feature-set)
- Dokumentation varierar i kvalitet
- Naming conventions kan vara inkonsekvent

## Azure vs AWS

**Välj Azure om:**
- Du kör Windows/Microsoft stack
- Hybrid cloud är viktigt
- Enterprise compliance och governance fokus

**Välj AWS om:**
- Linux-primärt
- Bredast möjliga tjänsteutbud krävs
- Startup/scale-up-miljö

## Further reading

- [Azure Architecture Center](https://docs.microsoft.com/en-us/azure/architecture/)
- [Azure Landing Zones](https://docs.microsoft.com/en-us/azure/cloud-adoption-framework/ready/landing-zone/)
- [Microsoft Learn](https://learn.microsoft.com/en-us/azure/)
- [Azure Well-Architected Framework](https://docs.microsoft.com/en-us/azure/architecture/framework/)
