# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Mintlify documentation site for Zaymo's Custom Integration API. Zaymo enables brands to sell directly within email through in-email widgets and purchase functionality. The documentation helps partners implement API endpoints on their servers that Zaymo calls to enable in-email commerce features.

## Development Commands

```bash
# Install Mintlify CLI globally
npm i -g mintlify

# Start local development server (runs at http://localhost:3000)
mintlify dev

# Troubleshooting: reinstall dependencies if dev server fails
mintlify install
```

**Note**: The Tailwind CSS warnings about "No utility classes detected" are normal and can be ignored - they don't affect functionality.

## Architecture

### Documentation Structure
- **Root configuration**: `docs.json` contains the main Mintlify configuration with navigation, theming, and API playground settings
- **Alternative config**: `examples/mint.json` appears to be an alternative or example configuration
- **OpenAPI spec**: `openapi.json` defines the complete API specification for Zaymo's Custom Integration API
- **Content organization**:
  - `/introduction.mdx` - Main landing page explaining Zaymo's value proposition
  - `/use-cases/` - Specific implementation scenarios (Product Upsells, Subscription Portal, Reactivation)
  - `/api-reference/` - API documentation and endpoint specifications
  - `/images/` - GIF demonstrations and branding assets

### API Architecture (from OpenAPI spec)
The API follows a standard pattern where partners implement endpoints on their servers that Zaymo calls:
- **Base URL pattern**: `https://api.partner-domain.com/zaymo/`
- **Authentication**: API key-based authentication required for all endpoints
- **Main endpoint categories**:
  - **Upsells**: `/zaymo/upsells/products` (GET), `/zaymo/upsells/add-product` (POST), `/zaymo/upsells/undo-add-product` (POST)
  - **Customer Portal**: Subscription management endpoints
  - **Reactivate**: Cancelled subscription reactivation endpoints

### Content Patterns
- All content files use `.mdx` format for enhanced React component support
- Consistent use of Mintlify components like `<Frame>`, `<Card>`, `<CardGroup>`
- Images stored in `/images/` with descriptive GIF demonstrations of features
- API reference pages leverage the OpenAPI specification for automatic endpoint documentation

## Development Notes

- The site uses Mintlify's automatic deployment via GitHub App integration
- Changes pushed to the main branch automatically deploy to production
- Local development requires running `mintlify dev` in the directory containing `mint.json`
- Two mint.json configurations exist - the root `docs.json` is the primary configuration