---
title:      "OpenTofu"
ring:       trial
quadrant:   tools
tags:       [infrastructure-as-code, iac, automation, open-source, terraform]
---

## Varför TRIAL?

OpenTofu är en open source fork av Terraform som skapades efter HashiCorps licensändring 2023. 100% Terraform-kompatibel, community-driven och CNCF-backed. Production-ready men fortfarande relativt ny - därför TRIAL för att ge det tid att bevisa long-term sustainability.

**Core strengths:**
- **Truly open source** - Mozilla Public License 2.0 (MPL 2.0)
- **Terraform-kompatibel** - Drop-in replacement för Terraform ≤1.5
- **Community-driven** - Inte beroende av en vendor
- **CNCF projekt** - Linux Foundation backing
- **Active development** - Rapid innovation och features
- **No licensing concerns** - Fritt att använda även i kommersiella produkter

## Varför OpenTofu skapades

**Background:**
- HashiCorp bytte Terraform license från MPL till BSL (Business Source License) augusti 2023
- BSL begränsar konkurrenter från att bygga managed Terraform services
- Community skapade OpenTofu för att bevara open source-versionen
- OpenTofu forked från Terraform 1.5.x

**Implications:**
- Terraform ≥1.6 är inte längre open source
- OpenTofu har samma features som Terraform 1.5 + nya community features
- Ecosystem split mellan Terraform och OpenTofu

## OpenTofu vs Terraform

**Compatibility:**
- ✅ Drop-in replacement för Terraform ≤1.5
- ✅ Samma HCL syntax
- ✅ Samma providers (Terraform Registry fungerar)
- ✅ Kan läsa Terraform state files

**Differences:**
- OpenTofu: Open source, community-driven, CNCF
- Terraform: BSL license, HashiCorp-controlled, proprietary features

**Migration:**
```bash
# Install OpenTofu
brew install opentofu

# Rename command (or alias)
alias terraform=tofu

# Existing code fungerar direkt
tofu init
tofu plan
tofu apply
```

## Key features

**Parity med Terraform:**
- All Terraform 1.5 functionality
- Same provider ecosystem
- Same module syntax
- Same state format

**OpenTofu-specifika features:**
- Enhanced state encryption (client-side)
- Improved error messages
- Community-requested features snabbare än Terraform

## Best practices

**Adoption strategy:**

**1. Nya projekt:**
- Börja direkt med OpenTofu
- Ingen migration behövs

**2. Befintliga Terraform-projekt:**
- Test i dev environment först
- Verify provider compatibility
- Gradual rollout till prod

**State management:**
- Same remote backend support (S3, Azure Blob, etc.)
- State files är kompatibla mellan Terraform och OpenTofu
- Lock-in risk minimerad

## När välja OpenTofu

✅ **Välj OpenTofu om:**
- Open source är viktigt för er organisation
- Vill undvika vendor lock-in
- Orolig för HashiCorps licenspolicy
- Vill bidra till community-driven tool
- Building managed IaC services (BSL begränsningar)

✅ **Välj Terraform om:**
- Terraform Cloud/Enterprise är central del av er stack
- Vill ha HashiCorp commercial support
- Behöver cutting-edge HashiCorp-only features (Terraform ≥1.6)
- Established på Terraform och inget behov att byta

## Community & Ecosystem

**Backing:**
- CNCF projekt
- 100+ companies och maintainers
- Snabb adoption i community

**Registry:**
- Använder Terraform Registry (kompatibilitet)
- OpenTofu Registry under utveckling
- Provider ecosystem intact

**Tools support:**
- Terraform Cloud alternatives (Spacelift, env0, Scalr) lägger till OpenTofu-support
- IDE plugins (VS Code) fungerar
- CI/CD integrations uppdateras

## Utmaningar

⚠️ **Tänk på:**
- Relativt nytt (2023) - long-term sustainability okänd ännu
- Terraform Cloud/Enterprise fungerar inte med OpenTofu
- Potentiell divergence från Terraform över tid
- Team kan behöva lära sig två tools om hybrid environment
- Mindre enterprise support än HashiCorp Terraform

## Roadmap & Future

**Current focus:**
- Feature parity med Terraform
- Enhanced security features
- Better testing capabilities
- Improved state management

**Long-term vision:**
- Community-driven innovation
- Stay compatible med Terraform providers
- Enhanced features baserat på community feedback

## Migration från Terraform

**Step-by-step:**

1. **Install OpenTofu:**
```bash
brew install opentofu
# eller via package manager
```

2. **Test kompatibilitet:**
```bash
tofu init
tofu plan  # Verify output matches terraform plan
```

3. **Update CI/CD:**
```yaml
# GitHub Actions example
- uses: opentofu/setup-opentofu@v1
  with:
    tofu_version: 1.6.0
```

4. **Team transition:**
- Communication och training
- Update documentation
- Gradual rollout

## Further reading

- [OpenTofu Documentation](https://opentofu.org/docs/)
- [OpenTofu GitHub](https://github.com/opentofu/opentofu)
- [OpenTofu Manifesto](https://opentofu.org/manifesto/)
- [CNCF OpenTofu Project](https://www.cncf.io/projects/opentofu/)
- [Terraform to OpenTofu Migration Guide](https://opentofu.org/docs/intro/migration/)
