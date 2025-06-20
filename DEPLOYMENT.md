# Deployment Guide

## Cloudflare Pages Deployment

This project is configured to deploy automatically to Cloudflare Pages from the GitHub repository.

### Build Settings for Cloudflare Pages

When setting up your Cloudflare Pages project, use these settings:

**Build Configuration:**
- **Framework preset**: `Astro`
- **Build command**: `npm run build`
- **Build output directory**: `dist`
- **Root directory**: `/` (default)
- **Node.js version**: `18` or `20`

**Environment Variables:**
No environment variables are required for basic deployment.

### Automatic Deployment

1. **Push to GitHub**: Any push to the `main` branch triggers automatic deployment
2. **Build Process**: Cloudflare Pages will:
   - Install dependencies with `npm ci`
   - Run `npm run build`
   - Deploy the contents of `./dist` to your custom domain
3. **Domain**: The site will be available at `https://predictstream.ai`

### Manual Deployment Testing

To test the build locally before pushing:

```bash
# Install dependencies
npm ci

# Build the site
npm run build

# Preview the built site
npm run preview
```

### Troubleshooting

**Build Failures:**
- Ensure Node.js version is 18 or 20
- Check that all dependencies install correctly
- Verify no missing environment variables

**Asset Issues:**
- Images and audio files in `/public` are served directly
- The podcast file is at `/predictstream-podcast.mp3`
- All assets use absolute paths from domain root

**Audio Player:**
- The podcast player requires the `predictstream-podcast.mp3` file in `/public`
- Browser autoplay policies may require user interaction
- Check browser console for debugging information

### GitHub Actions Removed

GitHub Actions workflows have been removed since Cloudflare Pages handles deployment directly from the repository. This eliminates the "Not Found" errors from GitHub Pages deployment attempts.