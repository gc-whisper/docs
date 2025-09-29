# GameRamp Documentation Repository

## Purpose
Official documentation for GameRamp API and SDKs, powered by Mintlify.

## About GameRamp
AI-powered player prediction and monetization platform for game developers. GameRamp provides APIs for:
- Player behavior predictions (payer likelihood)
- Dynamic store configurations
- Event tracking and analytics
- Authentication and token management

## About Mintlify
Modern documentation platform with:
- Git-based workflow
- MDX support (Markdown + React components)
- Automatic deployment via GitHub
- Built-in search and AI assistant

## Repository Structure
```
/
├── api-reference/      # REST API documentation
│   ├── authentication.mdx
│   ├── endpoints/      # API endpoints (auth, events, player)
│   └── testing.mdx
├── sdks/              # SDK documentation
│   └── unity/         # Unity SDK guide
├── docs.json          # Mintlify configuration
├── index.mdx          # Homepage
├── quickstart.mdx     # Getting started guide
├── GamerampDocumentation_v1.1 (1).pdf  # Source SDK specification
└── gr-api-docs.pdf    # Source API specification
```

## Critical Documentation Sources
**IMPORTANT**: All content published on Mintlify must be factually grounded in:
- **`GamerampDocumentation_v1.1 (1).pdf`** - Precise descriptions of GameRamp's SDK functionality
- **`gr-api-docs.pdf`** - Precise descriptions of GameRamp's API endpoints and specifications

These PDFs are the authoritative source of truth. Any documentation updates must strictly align with the specifications in these files.

## Development
```bash
mint dev   # Start local server at localhost:3000
```

## Deployment
Push to `main` branch → Auto-deploys via Mintlify GitHub integration

## Configuration
- **docs.json** - Site navigation, theming, and metadata
- **MDX files** - Documentation content with frontmatter
- **custom.css** - Custom styling overrides