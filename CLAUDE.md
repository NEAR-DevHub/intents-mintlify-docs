# Mintlify documentation for NEAR Intents

## Project overview
- Documentation for the NEAR Intents protocol — a cross-chain swap and intent settlement system
- Three primary audiences: **distribution channels** (apps integrating 1Click Swap API), **market makers** (solvers providing liquidity), and **direct integrators** (building on the verifier contract)
- Hosted via Mintlify — auto-deploys from `main` branch through the Mintlify dashboard

## Working relationship
- You can push back on ideas — this can lead to better documentation. Cite sources and explain your reasoning when you do so
- ALWAYS ask for clarification rather than making assumptions
- NEVER lie, guess, or make up information

## Project structure
```
/
├── docs.json                          # Mintlify config (navigation, theme, settings)
├── favicon.svg
├── getting-started/                   # Intro and first swap tutorial
├── integration/
│   ├── distribution-channels/         # 1Click Swap API integration
│   ├── market-makers/                 # Market maker guides, message bus
│   └── verifier-contract/             # Direct contract integration, deposits/withdrawals
├── api-reference/
│   ├── openapi.json                   # 1Click Swap API spec (OpenAPI 3.0)
│   ├── explorer-openapi.yaml          # Explorer API spec (OpenAPI 3.0)
│   ├── endpoint/                      # MDX pages for 1Click endpoints
│   └── explorer/                      # MDX pages for Explorer endpoints
├── resources/                         # FAQs, fees, chain support
├── security-compliance/               # Security, compliance, terms
└── images/
    ├── logo/                          # light.svg, dark.svg
    ├── chains/                        # SVG logos for supported chains
    └── diagrams/                      # SVG Architecture diagrams
```

## Mintlify config (`docs.json`)
- Theme: `maple`, primary color `#fb4d01` (orange)
- Two navigation tabs: **Home** and **API reference**
- Navigation uses nested groups with icons (Font Awesome names)
- Global anchors: Supported Chains, System Status, API Keys
- `appearance.strict: true` is enabled
- **IMPORTANT**: The `openapi` field belongs on navigation elements (tabs or groups), NOT as a top-level property. Placing it at the top level causes the CLI to try to validate `docs.json` as an OpenAPI spec

## OpenAPI integration
- Two specs: `/api-reference/openapi.json` (1Click Swap API) and `/api-reference/explorer-openapi.yaml` (Explorer API)
- The `openapi` array is set on the "API reference" tab in `docs.json`
- Individual MDX endpoint pages reference operations via frontmatter: `openapi: 'get /v0/tokens'`
- MDX pages add context beyond what's in the spec (tips, usage notes)

## Content strategy
- Document just enough for user success — not too much, not too little
- Prioritize accuracy and usability of information
- Make content evergreen when possible
- Search for existing information before adding new content. Avoid duplication unless it is done for a strategic reason
- Check existing patterns for consistency
- Start by making the smallest reasonable changes

## Frontmatter requirements for pages
- `title`: Clear, descriptive page title
- `description`: Concise summary for SEO/navigation
- Optional: `icon`, `sidebarTitle`
- API pages: `openapi` field referencing the endpoint

## MDX component patterns
- **Tutorials**: `<Steps>` / `<Step>` for step-by-step instructions
- **Code examples**: `<CodeGroup>` with curl, TypeScript, and Python variants
- **Tabbed content**: `<Tabs>` / `<Tab>` for alternate approaches or personas
- **Navigation cards**: `<CardGroup>` / `<Card>` for linking to related pages (commonly used at page end for "next steps")
- **Collapsible sections**: `<AccordionGroup>` / `<Accordion>` for FAQs
- **Callouts**: `<Info>`, `<Warning>`, `<Tip>`, `<Check>`
- Introduction pages typically use `<CardGroup>` to guide readers to subtopics

## Writing standards
- Second-person voice ("you")
- Prerequisites at start of procedural content
- Test all code examples before publishing
- Match style and formatting of existing pages
- Include both basic and advanced use cases
- Language tags on all code blocks
- Alt text on all images
- Relative paths for internal links

## Dev workflow
- No `package.json` — this is a pure Mintlify docs project
- Local preview: `mintlify dev` (runs at http://localhost:3000)
- Deployment: automatic from `main` via Mintlify dashboard
- Validate OpenAPI specs: `mintlify openapi-check <file>`

## Git workflow
- NEVER use `--no-verify` when committing
- Ask how to handle uncommitted changes before starting
- Create a new branch when no clear branch exists for changes
- Commit frequently throughout development
- NEVER skip or disable pre-commit hooks

## Do not
- Skip frontmatter on any MDX file
- Use absolute URLs for internal links
- Include untested code examples
- Make assumptions — always ask for clarification
- Place the `openapi` field at the top level of `docs.json`
