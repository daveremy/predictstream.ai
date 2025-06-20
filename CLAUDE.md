# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Commands

- `npm run dev` - Start development server at localhost:4321
- `npm run build` - Build production site to ./dist/
- `npm run preview` - Preview production build locally
- `npm run check` - Run Astro, ESLint, and Prettier checks
- `npm run fix` - Auto-fix ESLint and Prettier issues

## Architecture Overview

This is an **Astro 5.0** static site for PredictStream.ai with TypeScript and Tailwind CSS. The site uses Astro's file-based routing and component system with MDX support for content.

### Key Technologies
- **Astro 5.0** - Static site generator with islands architecture
- **TypeScript** - Full type safety across the codebase
- **Tailwind CSS** - Utility-first styling with custom theme
- **MDX** - Markdown with JSX for rich content
- **Astro Content Collections** - Type-safe content management

### Directory Structure
- `src/components/` - Reusable UI components organized by purpose
  - `widgets/` - Large page sections (Hero, Features, etc.)
  - `ui/` - Primitives (Button, Form, etc.)
  - `blog/` - Blog-specific components
  - `common/` - Shared components (Analytics, SEO)
- `src/content/` - Content collections with schema validation
- `src/data/` - Static data files and blog posts
- `src/layouts/` - Page layout templates
- `src/pages/` - File-based routing
- `src/config.yaml` - Site configuration and metadata

### Component Patterns
- Components follow Astro's islands architecture
- Props are strongly typed with TypeScript interfaces
- Styling uses Tailwind with consistent spacing and color systems
- SEO and analytics are handled through common components

### Content Management
- Blog posts use Astro Content Collections with frontmatter validation
- Content is written in MDX for rich formatting
- Images are optimized using Astro's Image component
- SEO metadata is centrally managed through config.yaml

### Styling System
- Tailwind CSS with custom theme variables
- Dark mode support with class-based toggling
- Mobile-first responsive design
- Custom animations and transitions

## Configuration Files
- `astro.config.ts` - Main Astro configuration and integrations
- `src/config.yaml` - Site metadata, SEO settings, and app configuration
- `tailwind.config.js` - Tailwind theme customization
- `src/navigation.ts` - Site navigation structure

## Sister Project: PredictStream3 Core Platform

This marketing website documents the **PredictStream3** core platform located at `../predictstream3/`. Understanding this relationship is crucial for maintaining consistency between the public website and the actual technology.

### PredictStream3 Architecture
- **Backend**: Python with LangGraph for multi-agent orchestration
- **LLM Integration**: OpenAI GPT-4 and Google Gemini models
- **Frontend**: React 18 + TypeScript with Vite build system
- **Styling**: Tailwind CSS (shared design system)
- **Real-time Processing**: Event-driven pipeline with four processing phases

### Core Pipeline Phases
1. **Semantic Phase** - Event normalization and enhancement
2. **Context Phase** - Domain context and entity enrichment
3. **Prediction Phase** - AI-powered predictions using LLMs
4. **Action Phase** - Automated response generation

### PredictStream3 Development Commands
```bash
# Core platform (from ../predictstream3/)
python cli.py                    # Run CLI demo
python cli.py --num-events 10    # Generate specific number of events
python data_generator/synthetic_events.py  # Generate test data

# UI development (from ../predictstream3/ui/)
npm run dev                      # Start React dev server on port 3001
npm run build                    # Build React app
```

### Content Relationship
- **Website Content**: Should reflect actual capabilities demonstrated in PredictStream3
- **Use Cases**: Examples shown on website should correspond to working demos in PredictStream3
- **Documentation**: Technical details should align with PredictStream3 implementation
- **Branding**: Visual elements and messaging should be consistent across both projects

### When Working on Website Content
- Reference `../predictstream3/README.md` for current platform capabilities
- Check `../predictstream3/docs/` for technical documentation
- Verify demos in `../predictstream3/demo/` when writing about platform features
- Ensure pipeline descriptions match the four-phase architecture in PredictStream3