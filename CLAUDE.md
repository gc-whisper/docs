# Mintlify Documentation Knowledge Base

## Overview
Mintlify is a modern, AI-native documentation platform designed for developers. It provides beautiful, interactive documentation sites with built-in AI assistance, search functionality, and extensive customization options.

## Core Features
- **AI-Powered**: Built-in AI assistant for documentation
- **Git-Based Workflow**: Integrates with GitHub/GitLab for version control
- **MDX Support**: Combines Markdown with React components
- **API Documentation**: Full OpenAPI/Swagger support
- **Interactive Components**: Rich set of UI components for documentation
- **Customizable Themes**: Extensive branding and styling options
- **Analytics Integration**: Support for multiple analytics providers

## Quick Start Process

### 1. Installation
```bash
npm i -g mint  # Requires Node.js v19+
```

### 2. Project Structure
```
/
├── docs.json          # Global configuration file
├── index.mdx          # Homepage
├── api/               # API documentation (optional)
│   └── openapi.json   # OpenAPI specification
└── pages/             # Documentation pages
    └── *.mdx          # MDX documentation files
```

### 3. Local Development
```bash
mint dev  # Run local development server
```

### 4. Deployment
- Automatic via GitHub App integration
- Manual via web editor
- Preview deployments for pull requests

## Configuration (docs.json)

### Basic Structure
```json
{
  "name": "Documentation Title",
  "logo": {
    "light": "/logo/light.svg",
    "dark": "/logo/dark.svg"
  },
  "favicon": "/favicon.svg",
  "colors": {
    "primary": "#0D9373",
    "light": "#55D799",
    "dark": "#0D9373",
    "background": {
      "dark": "#0F0F0F",
      "light": "#FFFFFF"
    }
  },
  "navigation": [
    {
      "group": "Getting Started",
      "pages": ["introduction", "quickstart"]
    },
    {
      "group": "API Reference",
      "pages": ["api/endpoints"]
    }
  ],
  "tabs": [
    {
      "name": "API Reference",
      "url": "api"
    }
  ]
}
```

### Key Configuration Options
- **name**: Site name
- **logo**: Light/dark mode logos
- **favicon**: Site favicon
- **colors**: Theme colors (primary, light, dark, background)
- **navigation**: Structure of documentation sidebar
- **tabs**: Top-level navigation tabs
- **topbarLinks**: External links in header
- **topbarCtaButton**: Call-to-action button in header
- **analytics**: Analytics provider configurations
- **feedback**: Enable feedback widgets
- **search**: Search configuration
- **modeToggle**: Light/dark mode toggle settings

## Page Structure (MDX)

### Frontmatter Options
```yaml
---
title: "Page Title"              # Required
description: "Page description"   # SEO description
sidebarTitle: "Sidebar Title"    # Short navigation title
icon: "book"                      # Icon (Font Awesome/Lucide)
tag: "NEW"                        # Badge/tag
mode: "default"                   # Layout mode
---
```

### Layout Modes
- **default**: Standard layout with sidebar and TOC
- **wide**: Hides TOC for extra width
- **custom**: Minimal layout (navbar only)
- **frame**: Preserves sidebar navigation
- **center**: Centers content, removes sidebar

## Components

### Text & Structure
- Headers (H1-H6)
- Lists (ordered/unordered)
- Tables
- Blockquotes
- Code blocks with syntax highlighting

### Interactive Components
- **Accordion**: Collapsible content sections
- **Tabs**: Tabbed content
- **CodeGroup**: Multiple code examples in different languages
- **Card**: Card-based layouts
- **CardGroup**: Grid of cards
- **Steps**: Step-by-step instructions
- **Expandable**: Show/hide content
- **Tooltip**: Hover tooltips

### Visual Components
- **Callout**: Highlighted information boxes (info, warning, danger, success)
- **Frame**: Embed external content
- **Image**: Responsive images
- **Icon**: Font Awesome/Lucide icons
- **Banner**: Site-wide announcements

### API Documentation Components
- **Field**: API parameter documentation
- **ParamField**: Detailed parameter descriptions
- **ResponseField**: Response parameter documentation
- **ResponseExample**: API response examples

## API Documentation Setup

### OpenAPI Integration

#### 1. Add OpenAPI Spec
Place OpenAPI spec file (JSON/YAML) in project:
```
/api/openapi.json
```

#### 2. Configure in docs.json
```json
{
  "openapi": "/api/openapi.json",
  "api": {
    "baseUrl": "https://api.example.com",
    "auth": {
      "method": "bearer"
    }
  }
}
```

#### 3. Reference Endpoints in MDX
```yaml
---
title: "Get Users"
openapi: "GET /users"
---
```

Or for multiple specs:
```yaml
---
title: "Create User"
openapi: "/api/openapi-v2.json POST /users"
---
```

### Authentication Methods
- **API Key**: Header or query parameter
- **Bearer Token**: Authorization header
- **Basic Auth**: Username/password
- **OAuth2**: OAuth flow support

## Styling & Branding

### Color Customization
```json
{
  "colors": {
    "primary": "#0D9373",      // Main brand color
    "light": "#55D799",        // Light mode accent
    "dark": "#0D9373",         // Dark mode accent
    "background": {
      "dark": "#0F0F0F",       // Dark mode background
      "light": "#FFFFFF"       // Light mode background
    },
    "anchors": {
      "from": "#0D9373",       // Gradient start
      "to": "#55D799"          // Gradient end
    }
  }
}
```

### Typography
- Default fonts: Inter (body), Geist Mono (code)
- Customizable via CSS overrides
- Supports custom font imports

### Custom CSS
Add custom styles via:
1. Custom CSS files
2. Inline styles in MDX
3. Theme overrides in docs.json

## Analytics Integration

### Supported Providers
- Google Analytics 4
- Google Tag Manager
- Amplitude
- Mixpanel
- PostHog
- Segment
- Heap
- HotJar
- LogRocket
- Plausible
- Fathom
- Pirsch
- Clearbit
- Koala
- Hightouch

### Configuration Example
```json
{
  "analytics": {
    "ga4": {
      "measurementId": "G-XXXXXXXXXX"
    },
    "mixpanel": {
      "projectToken": "your-project-token"
    }
  }
}
```

### Tracked Events
- Page views
- Search queries
- Feedback (thumbs up/down)
- Code block copies
- API playground interactions
- Accordion opens/closes
- Navigation clicks
- AI assistant usage

## Custom Domain Setup

### 1. Dashboard Configuration
1. Go to Mintlify dashboard
2. Navigate to Settings > Domain Setup
3. Enter custom domain (e.g., `docs.example.com`)

### 2. DNS Configuration
Add CNAME record:
- **Type**: CNAME
- **Host**: docs (or your subdomain)
- **Value**: cname.vercel-dns.com

### 3. SSL/HTTPS
- Automatic SSL certificate provisioning
- For Cloudflare: Enable "Full (strict)" SSL mode

## Deployment

### GitHub Integration
1. Install Mintlify GitHub App
2. Connect repository
3. Automatic deployment on push to main branch
4. Preview deployments for pull requests

### Manual Deployment
1. Use web editor for quick updates
2. Click "Publish" to deploy changes
3. Changes reflect within minutes

### CI/CD Checks
- Automatic validation of docs.json
- MDX syntax checking
- OpenAPI spec validation
- Broken link detection

## Best Practices

### Content Organization
1. **Logical grouping**: Group related pages together
2. **Progressive disclosure**: Start simple, add complexity
3. **Clear navigation**: Use descriptive titles and sidebar organization
4. **Consistent structure**: Follow same pattern across pages

### API Documentation
1. **Complete OpenAPI specs**: Include all endpoints, parameters, responses
2. **Code examples**: Provide examples in multiple languages
3. **Authentication docs**: Clear auth setup instructions
4. **Error handling**: Document error codes and responses
5. **Versioning**: Support multiple API versions if needed

### Performance
1. **Image optimization**: Use appropriate formats and sizes
2. **Code splitting**: Break large docs into multiple pages
3. **Search optimization**: Use clear titles and descriptions
4. **Lazy loading**: For embedded content and images

### SEO
1. **Meta descriptions**: Add descriptions to all pages
2. **Structured data**: Use appropriate headers and semantic HTML
3. **Sitemap**: Automatically generated
4. **Open Graph tags**: Social media preview optimization

## CLI Commands

```bash
mint dev              # Start local development server
mint build           # Build documentation
mint validate        # Validate configuration
mint deploy          # Manual deployment
```

## File Formats

### MDX Files
- Combine Markdown with JSX components
- Support frontmatter for metadata
- Can import and use React components
- Syntax highlighting for code blocks

### OpenAPI Specs
- Support OpenAPI 3.0+
- JSON or YAML format
- Can reference multiple spec files
- Automatic endpoint documentation generation

## Advanced Features

### Monorepo Support
- Multiple documentation sites in one repository
- Shared components and configurations
- Independent deployment configurations

### Internationalization
- Multiple language support
- Language switcher component
- Separate navigation per language
- RTL language support

### Search
- Built-in search functionality
- Algolia integration option
- Search analytics
- Custom search filters

### AI Features
- AI-powered search
- Contextual AI assistant
- Smart suggestions
- Question answering

## Migration from Other Platforms

### From GitBook
- MDX compatible format
- Similar component structure
- Git-based workflow

### From Docusaurus
- MDX support
- React component compatibility
- Similar configuration structure

### From ReadMe
- OpenAPI support
- API playground features
- Analytics integration

## Troubleshooting

### Common Issues
1. **Build failures**: Check docs.json syntax
2. **Missing pages**: Verify navigation configuration
3. **Broken links**: Use relative paths
4. **Style issues**: Clear browser cache
5. **API playground errors**: Verify OpenAPI spec

### Debug Mode
```bash
mint dev --debug  # Run with debug output
```

## GameRamp Documentation Setup Notes

### Key Considerations for GameRamp
1. **API-First Documentation**: Focus on OpenAPI integration for GameRamp APIs
2. **SDK Documentation**: Use CodeGroup components for multi-language examples
3. **Interactive Playground**: Enable API playground for testing
4. **Brand Consistency**: Apply GameRamp colors, logos, and typography
5. **Authentication Docs**: Clear setup for GameRamp API keys/tokens

### Recommended Structure for GameRamp
```
/
├── docs.json              # GameRamp branded configuration
├── index.mdx              # GameRamp overview/welcome
├── quickstart.mdx         # Getting started with GameRamp
├── guides/                # Integration guides
│   ├── authentication.mdx
│   ├── webhooks.mdx
│   └── best-practices.mdx
├── api/                   # API Reference
│   ├── openapi.json       # GameRamp OpenAPI spec
│   └── endpoints/         # Individual endpoint docs
├── sdks/                  # SDK Documentation
│   ├── javascript.mdx
│   ├── python.mdx
│   └── unity.mdx
└── examples/              # Code examples
    └── tutorials/         # Step-by-step tutorials
```

### Next Steps
1. Review GameRamp PDFs for content structure
2. Extract API specifications
3. Convert content to MDX format
4. Apply GameRamp branding
5. Configure docs.json with GameRamp settings
6. Set up deployment pipeline