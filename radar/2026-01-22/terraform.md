---
title:      "Terraform"
ring:       adopt
quadrant:   tools
tags:       [infrastructure-as-code, iac, automation, multi-cloud]
---

## Varför ADOPT?

Terraform är industry standard för Infrastructure as Code med brett stöd för alla stora cloud providers och hundratals andra plattformar. Deklarativ syntax, robust state management och mogen tooling gör det till första valet för att hantera infrastruktur som kod.

**Core strengths:**
- **Multi-cloud** - En syntax för AWS, Azure, GCP, Kubernetes och 3000+ providers
- **Declarative** - Beskriv önskat state, Terraform hanterar resten
- **State management** - Robust tracking av vad som existerar
- **Modular** - Återanvändbara modules för DRY-princip
- **Plan before apply** - Se vad som kommer att ändras innan execution

## Key concepts

**HCL (HashiCorp Configuration Language):**
```hcl
resource "aws_instance" "web" {
  ami           = "ami-0c55b159cbfafe1f0"
  instance_type = "t3.micro"
  
  tags = {
    Name = "WebServer"
  }
}
```

**Terraform workflow:**
1. `terraform init` - Installera providers och modules
2. `terraform plan` - Preview changes
3. `terraform apply` - Utför ändringar
4. `terraform destroy` - Ta bort resurser

**State:**
- Lagrar current state av din infrastruktur
- Remote backends (S3, Azure Blob, Terraform Cloud) för team collaboration
- State locking för att förhindra conflicts

## Best practices

**Project structure:**
```
terraform/
├── environments/
│   ├── dev/
│   ├── staging/
│   └── prod/
├── modules/
│   ├── network/
│   ├── compute/
│   └── database/
└── shared/
    └── backend.tf
```

**State management:**
- **Remote state** - S3/Azure Blob med state locking (DynamoDB/Azure Storage)
- **Workspaces** för environments (eller separata state files)
- Never commit state files till Git
- Backup state regelbundet

**Code quality:**
- `terraform fmt` - Format code
- `terraform validate` - Syntax validation
- `terraform plan` - Always preview before apply
- `tflint` - Linting för best practices
- `checkov` / `tfsec` - Security scanning

**Modules:**
- Skapa återanvändbara modules för common patterns
- Version modules (Git tags eller Terraform Registry)
- Azure Verified Modules (AVM) för Azure
- AWS modules från Terraform Registry

**Variables & Outputs:**
- Använd variables för flexibilitet
- Sensitive values via environment variables eller secret managers
- Outputs för att dela data mellan modules/stacks

## Advanced features

**Dynamic blocks:**
- Generera repetitiv configuration
- Loop över lists och maps

**Data sources:**
- Query existing infrastructure
- Integration med external systems

**Provisioners (använd sparsamt):**
- `local-exec` och `remote-exec`
- Prefer cloud-init eller configuration management istället

## Terraform Cloud/Enterprise

**Benefits:**
- Remote execution och state
- Team collaboration
- Policy as Code (Sentinel)
- Private module registry
- VCS integration (GitHub, GitLab)

**Free tier:**
- Up to 5 users
- Remote state och execution
- Private modules

## Utmaningar

⚠️ **Tänk på:**
- State drift - resurser ändrade utanför Terraform
- Import av existing infrastructure kan vara komplext
- Vissa providers har sämre kvalitet än andra
- Upgrade-path mellan major versions kan vara jobbig
- License-ändringar 2023 (BSL) - se OpenTofu för open source-alternativ

## Terraform vs alternativ

**Terraform vs CloudFormation/ARM:**
- Terraform: Multi-cloud, bättre syntax, större community
- CloudFormation/ARM: Djupare integration med AWS/Azure

**Terraform vs Pulumi:**
- Terraform: HCL, deklarativ, established
- Pulumi: Riktiga programmeringsspråk (Python, TypeScript), mer flexibility

**Terraform vs Ansible:**
- Terraform: Infrastructure provisioning (create/destroy)
- Ansible: Configuration management (configure existing resources)
- Använd ofta båda tillsammans

## Migrering och adoption

**Start small:**
1. Börja med ny infrastruktur
2. Terraform endast i dev först
3. Bygga upp modules library
4. Importera existing resources stegvis
5. Rulla ut till staging/prod

**Team enablement:**
- Training på Terraform basics
- Kodreview-process
- Shared modules och best practices
- CI/CD integration

## Further reading

- [Terraform Documentation](https://www.terraform.io/docs)
- [Terraform Best Practices](https://www.terraform-best-practices.com/)
- [Terraform Registry](https://registry.terraform.io/)
- [HashiCorp Learn](https://learn.hashicorp.com/terraform)
- [Azure Verified Modules](https://azure.github.io/Azure-Verified-Modules/)
