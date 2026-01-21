# GitHub Copilot Instructions - techradar.se

## Project Overview

**techradar.se** är en interaktiv techradar som visar vad som är aktuellt och hetast att lära sig inom infrastructure engineering och devops. Projektet innehåller både data om teknologier/verktyg och källkoden för webbplatsen.

Projektet är baserat på **AOE Technology Radar v4+** som använder Next.js för frontend-visualisering.

## Purpose

Hjälpa infrastructure engineers att navigera i tekniklandskapet och fokusera sitt lärande. Radarn visualiserar:

- **Core skills** (ADOPT) - Produktionsklara teknologier som är essentiella att behärska
- **Emerging technologies** (TRIAL) - Teknologier på gång som är värda att börja lära sig
- **Learning opportunities** (ASSESS) - Vad som finns på horisonten att utvärdera och utforska
- **Deprioritize** (HOLD) - Vad man kan lägga åt sidan eller undvika

Målet är att ge infrastructure engineers:
- Koll på vad de behöver lära sig för att vara relevanta
- Insikt i vilka teknologier som är på väg in
- Förståelse för vilka skills som är core vs nice-to-have
- Vägledning om vad de kan deprioritera eller undvika

## Reference Implementation

`doc-techradar/` mappen innehåller ett fungerande exempel på hur sidan ska se ut och fungera. Detta är referensimplementationen för stil, layout och funktionalitet.

## Project Structure

```
techradar/
├── radar/                      # Radar data som markdown filer
│   └── YYYY-MM-DD/            # En mapp per release (t.ex. 2025-02-01/)
│       ├── kubernetes.md       # En .md fil per teknologi
│       ├── terraform.md
│       └── ...
├── public/                     # Statiska assets
│   ├── logo.svg               # Logo för sidan
│   └── fonts/                 # Custom fonts
├── config.json                 # Huvudkonfiguration för radarn
├── about.md                    # Om-sida och hjälptext
├── custom.css                  # CSS overrides för styling
├── package.json                # NPM dependencies (aoe_technology_radar)
└── docs/                       # Dokumentation
```

## Data Structure

### Markdown-based Technology Entries

Varje teknologi beskrivs i en egen markdown-fil under `radar/YYYY-MM-DD/teknologi-namn.md`.

**Filnamn**: Lowercase med bindestreck (kebab-case), t.ex. `kubernetes.md`, `infrastructure-as-code.md`

**Frontmatter struktur** (YAML):

```markdown
---
title:      "Kubernetes"
ring:       adopt
quadrant:   platforms-and-operations
tags:       [containers, orchestration, cloud-native]
guid:       a1b2c3d4-e5f6-7890-abcd-ef1234567890
---

Beskrivning av teknologin här. Markdown-formaterad text som förklarar:
- Vad teknologin är
- Varför den är i denna ring
- Användningsområden
- Länkar till mer information

Exempel:
Kubernetes is the industry standard for container orchestration...

Further reading:
- [Kubernetes.io](https://kubernetes.io)
- [CNCF Landscape](https://landscape.cncf.io)
```

**Frontmatter fält**:
- `title` - Teknologins namn (visas i UI)
- `ring` - adopt | trial | assess | hold
- `quadrant` - languages-and-frameworks | tools | methods-and-patterns | platforms-and-operations
- `tags` - Array av relevanta tags för filtrering
- `guid` - Unik UUID för teknologin (generera med uuidgen eller liknande)

### Ring Definitions

- **ADOPT** - Produktionsredo, rekommenderas starkt
- **TRIAL** - Moget nog att prova i mindre produktionsprojekt
- **ASSESS** - Värt att utvärdera och lära sig om
- **HOLD** - Var försiktig, överväg alternativ

### Quadrants

- **Languages & Frameworks** - Programmeringsspråk och utvecklingsramverk (Java, Python, Kotlin, Terraform, etc.)
- **Tools** - Konkreta verktyg och produkter (Gradle, Jenkins, ArgoCD, Sonarqube, etc.)
- **Methods & Patterns** - Metoder, patterns och praxis (DevOps, Microservices, API-First, Trunk-based development)
- **Platforms & Operations** - Plattformar och infrastruktur (Kubernetes, Container Platform, Cloud Foundations, etc.)

### Categories (exempel för infrastructure/devops)

- Container & Orchestration (Kubernetes, Docker, Podman)
- CI/CD & Automation (Jenkins, ArgoCD, GitHub Actions, GitLab CI)
- Infrastructure as Code (Terraform, Ansible, Pulumi, CloudFormation)
- Observability & Monitoring (Prometheus, Grafana, OpenTelemetry, DataDog)
- Security & Compliance (Checkov, Policy as Code, DevSecOps practices)
- Cloud Platforms (AWS, Azure, GCP, Private Cloud)
- Networking (Service Mesh, Istio, Envoy, Load Balancers)
- Databases & Storage (PostgreSQL, MongoDB, Redis, S3)
- GitOps (ArgoCD, Flux, GitOps practices)
- Platform Engineering (Backstage, Internal Developer Platforms)
- Testing (Molecule, Test automation, Synthetic monitoring)
- API Management (REST, GraphQL, OpenAPI, API Gateways)

## Technology Stack

### Core Platform
- **Framework**: AOE Technology Radar v4+ (NPM package: `aoe_technology_radar`)
- **Build Tool**: Node.js + NPM för frontend build
- **Static Site Generation**: Next.js-baserad (via aoe_technology_radar)
- **Styling**: CSS overrides via `custom.css`
- **Data Format**: Markdown-filer med YAML frontmatter

### Build & Deployment
```bash
npm install              # Installera dependencies
npm run build            # Bygg statisk site (aoe_technology_radar build)
npm run serve            # Lokal dev server (aoe_technology_radar serve)
```

### Optional Backend (för produktion)
- Spring Boot (Java) för att servera statiska filer
- Kan deployas som static site till Netlify/Vercel/GitHub Pages
- Eller som containeriserad app med backend

### Visualisering
- D3.js (ingår i aoe_technology_radar)
- Interaktiv radar med hover/click
- Responsive design
- Tag-baserad filtrering

## Coding Standards

### General
- Följ AOE Technology Radar konventioner
- Markdown-filer för all radar content
- YAML frontmatter för metadata
- Kebab-case för filnamn
- En fil per teknologi

### File Naming & Structure
- Technology files: `kebab-case.md` (e.g., `kubernetes.md`, `infrastructure-as-code.md`)
- Release folders: `YYYY-MM-DD/` (e.g., `2025-02-01/`)
- Static assets: `/public/` directory
- Config: `config.json` i root
- Custom styles: `custom.css` i root
- About page: `about.md` i root

### Markdown Content Guidelines
- Clear, concise technology descriptions (in English)
- Explain WHY the technology is in this ring
- Include concrete use cases
- Add links to further reading
- Follow doc-techradar style and tone
- Keep technical terminology in English

### YAML Frontmatter
- Alltid inkludera alla required fields
- Generera nya GUIDs med `uuidgen`
- Tags ska vara relevanta och konsekventa
- Ring och quadrant ska matcha config.json

### Custom CSS
- Minimal CSS overrides
- Använd CSS custom properties (variables) från tema
- Bevara responsivitet
- Testa på mobil och desktop

## Component Guidelines

### Radar Visualization
- Använd AOE Technology Radar's inbyggda visualisering
- Färger definierade i config.json
- Interaktiv hover/click via framework
- Responsive via CSS overrides
- Smooth animations from framework

### Config.json Inställningar
- `showChart: true` - Visa radar chart
- `showTagFilter: true` - Aktivera tag-filtrering
- `showQuadrantList: true` - Visa lista per quadrant
- `showEmptyRings: false` - Dölj tomma rings
- `sections: ["radar", "tags", "list"]` - Aktiva sektioner

### Technology Detail Pages
- Genereras automatiskt från markdown
- Visa frontmatter metadata
- Render markdown content
- "Edit on GitHub" länk via editUrl
- Links till relaterade teknologier via tags

### Navigation
- Header med logo (definierad i config.json)
- Quadrant navigation
- Ring filter
- Tag filter
- Search/filter funktioner från framework

## Data Management Guidelines

### Adding Technologies
1. Skapa en ny markdown-fil i senaste release-mappen (t.ex. `radar/2025-02-01/`)
2. Använd kebab-case för filnamn
3. Inkludera komplett YAML frontmatter
4. Generera ny GUID med `uuidgen`
5. Skriv tydlig beskrivning med reasoning
6. Lägg till relevanta tags
7. Inkludera "Further reading" länkar

### Updating Technologies
- Review teknologier regelbundet (minst varje kvartal)
- När en teknologi flyttas till ny ring, skapa ny release-mapp
- Dokumentera större förändringar i CHANGELOG
- Använd semantic versioning för releases

### Release Management
- En release = en daterad mapp (YYYY-MM-DD)
- Varje release kan innehålla nya eller uppdaterade teknologier
- Framework visar automatiskt "New" eller "Changed" badges
- Older releases behålls för historik

### Markdown Format Guidelines
```markdown
---
title:      "Technology Name"
ring:       adopt|trial|assess|hold
quadrant:   languages-and-frameworks|tools|methods-and-patterns|platforms-and-operations
tags:       [tag1, tag2, tag3]
guid:       xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
---

Första stycket: Kort beskrivning av teknologin.

Andra stycket: Varför är den i denna ring? Vad är use cases?

Tredje stycket (optional): Mer detaljer, warnings, best practices.

Further reading:
- [Link 1](https://example.com)
- [Link 2](https://example.com)
```

## Performance Considerations

- Lazy load teknologi-detaljer
- Optimize radar rendering för många items
- Cache data när möjligt
- Minimize bundle size
- Use code splitting
- Optimize images och assets

## Accessibility

- Semantic HTML
- ARIA labels där behövs
- Keyboard navigation
- Focus indicators
- Color contrast (WCAG AA minimum)
- Screen reader friendly
- Alt text för alla images

## Language Guidelines

### Content Language Strategy
- **Technology descriptions**: English (follows industry standard and doc-techradar reference)
- **About page** (`about.md`): Swedish (explains purpose and usage for Swedish audience)
- **Technical terms**: Always English (Kubernetes, GitOps, Terraform, etc.)
- **UI labels**: Can be customized in config.json if needed

### Rationale
- Tekniska beskrivningar på engelska = lättare att dela och underhålla
- Följer referensimplementationen (doc-techradar)
- Matchar tech community standards
- Enklare för internationell användning
- Swedish about.md ger lokal kontext

### Example Content
```markdown
---
title:      "Kubernetes"
ring:       adopt
quadrant:   platforms-and-operations
tags:       [containers, orchestration, cloud-native]
guid:       a1b2c3d4-...
---

Kubernetes is the industry standard for container orchestration...
```

## Version Control

### Commit Messages
Follow conventional commits:
- `feat:` ny funktionalitet
- `fix:` buggfix
- `data:` ändringar i tech radar data
- `docs:` dokumentation
- `style:` formatering
- `refactor:` kod omstrukturering
- `test:` tester
- `chore:` build, dependencies

### Branching
- `main` - production-ready kod
- `develop` - development branch
- `feature/*` - nya features
- `data/*` - data updates
- `fix/*` - bugfixes

## Testing

- Unit tests för utilities och helpers
- Component tests för UI komponenter
- Validate JSON data schema
- E2E tests för kritiska user flows
- Visual regression tests för radar

## Documentation

- README med setup instructions
- CONTRIBUTING guide för bidragsgivare
- Data schema documentation
- Component documentation (Storybook rekommenderas)
- Deployment guide

## Content Philosophy

### Technology Selection Criteria
- Relevant för infrastructure engineering/devops
- Aktivt underhållet och community support
- Praktisk användning i produktionsmiljöer
- Balans mellan cutting-edge och proven tech
- Tydlighet kring var i learning journey teknologin passar in (core skill vs emerging vs exploratory)

### Objectivity
- Basera bedömningar på fakta och community-feedback
- Var transparent om reasoning (särskilt varför något är ADOPT vs HOLD)
- Uppdatera när ny information kommer
- Acceptera olika perspektiv
- Förklara business value och learning investment för varje teknologi

### Swedish Focus
- Prioritera teknologier relevanta för svenska marknaden
- Inkludera global context
- Referera till svenska communities när relevant

## Future Enhancements

Potential features att överväga:
- User submissions för nya teknologier
- Voting system för community input
- Historical view (visa radar över tid)
- Comparison view (jämför olika tidpunkter)
- Personal radar (spara egen tech stack)
- RSS feed för updates
- API för programmatisk access
- Integration med GitHub trends
- Swedish tech meetup calendar

## Resources

- ThoughtWorks Tech Radar (inspiration)
- CNCF Landscape
- State of DevOps Reports
- Stack Overflow Developer Survey
- GitHub Octoverse

## Contact & Contribution

- Välkomna contributions via pull requests
- Diskutera större ändringar i issues först
- Följ code of conduct
- Respektera olika åsikter och perspektiv
