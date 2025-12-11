# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

PIXL is a static website project built with Vite and Tailwind CSS 4. It's a modern, dark-themed landing page with custom branding and styling for a media platform. The project uses the new Tailwind CSS 4 architecture with native CSS variables and `@theme` configuration.

## Development Commands

```bash
# Start development server with hot reload
npm run dev

# Build for production (not configured yet)
# Tests (not configured yet)
```

**Note**: The Vite dev server is configured with `usePolling: true` for file watching to ensure hot module replacement (HMR) works reliably on macOS.

## Tech Stack

- **Build Tool**: Vite 7.x with native ES modules
- **Styling**: Tailwind CSS 4.x with Vite plugin (`@tailwindcss/vite`)
- **Formatting**: Prettier with Tailwind plugin for class sorting

## Project Structure

- `index.html` - Landing page with authentication prompts
- `feed.html` - Basic feed layout (work in progress)
- `styles.css` - Main stylesheet with Tailwind imports and custom theme
- `vite.config.js` - Vite configuration with Tailwind plugin
- `public/fonts/` - Custom "Departure Mono" font files
- `public/images/` - Static assets including background images and white noise texture

## Styling Architecture

### Custom Theme Variables

The project uses Tailwind CSS 4's `@theme` directive to define custom design tokens in `styles.css`:

- **Colors**:
  - `pixl` (#eca749) - Brand orange/gold color
  - `pixl-light` (#eeeeee) - Light gray for text
  - `pixl-dark` (#090909) - Almost black for backgrounds

- **Typography**: Uses "Departure Mono" as the default monospace font loaded via `@font-face`

### Color Usage Patterns

- Primary brand color: `bg-pixl`, `text-pixl`, `border-pixl`
- Text on dark backgrounds: `text-pixl-light`
- Dark backgrounds: `bg-pixl-dark`
- Opacity modifiers are heavily used (e.g., `bg-pixl-dark/50`, `border-pixl/60`)
- Hover and active states use progressive opacity changes

### Common UI Patterns

- Buttons use semi-transparent backgrounds with border and hover states
- Background images use custom mask utilities (e.g., `mask-l-from-80%`)
- SVG graphics are inline for the PIXL logo and pictogram
- Fixed/absolute positioning for decorative elements (white noise footer, background image)
- Responsive breakpoints: mobile-first with `md:` and `xl:` variants

## Important Notes

- **Tailwind v4**: This project uses the latest Tailwind CSS 4 with `@import "tailwindcss"` syntax and `@theme` configuration, not the traditional `tailwind.config.js` approach
- **Font Loading**: The Departure Mono font is critical to the brand identity - ensure font files are present in `/public/fonts/`
- **Static Assets**: Background images and textures in `/public/images/` are referenced directly in HTML
- **Dark Theme**: The entire site uses a dark color scheme (`meta name="color-scheme" content="dark"`)
- **No Backend**: This is a static frontend project - all links currently point to `/feed` as placeholders
