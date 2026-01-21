# techradar.se

En interaktiv tech radar som visar vad som är aktuellt och hetast att lära sig inom infrastructure engineering och devops.

![Tech Radar](screenshot.png)

## Snabbstart

```bash
# Installera dependencies
npm install

# Kör lokal dev server
npm run serve

# Bygg statisk site
npm run build
```

Öppna sedan [http://localhost:3001](http://localhost:3001) i din webbläsare.

## Projektstruktur

```
techradar/
├── radar/                    # Radar data som markdown filer
│   └── 2025-02-01/          # Release-mapp (YYYY-MM-DD)
│       ├── kubernetes.md    # En fil per teknologi
│       ├── terraform.md
│       └── ...
├── public/                  # Statiska assets (logo, fonts, etc.)
├── config.json              # Huvudkonfiguration
├── about.md                 # Om-sida (svenska)
├── custom.css               # CSS overrides
├── package.json             # NPM dependencies
└── README.md                # Denna fil
```

## Lägga till ny teknologi

1. Skapa en ny markdown-fil i `radar/2025-02-01/teknologi-namn.md`
2. Använd kebab-case för filnamn (t.ex. `infrastructure-as-code.md`)
3. Lägg till YAML frontmatter:

```markdown
---
title:      "Technology Name"
ring:       adopt|trial|assess|hold
quadrant:   languages-and-frameworks|tools|methods-and-patterns|platforms-and-operations
tags:       [tag1, tag2, tag3]
guid:       xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
---

Beskrivning av teknologin på engelska...

Further reading:
- [Link](https://example.com)
```

4. Generera ny GUID med: `uuidgen`

## Rings

- **Adopt** - Produktionsredo, rekommenderas starkt
- **Trial** - Moget nog att prova i mindre produktionsprojekt
- **Assess** - Värt att utvärdera och lära sig om
- **Hold** - Var försiktig, överväg alternativ

## Quadrants

- **Languages & Frameworks** - Programmeringsspråk och utvecklingsramverk
- **Tools** - Konkreta verktyg och produkter
- **Methods & Patterns** - Metoder, patterns och praxis
- **Platforms & Operations** - Plattformar och infrastruktur

## Baserat på

Detta projekt använder [AOE Technology Radar v4+](https://github.com/AOEpeople/aoe_technology_radar) som grund.

## Licens

MIT
