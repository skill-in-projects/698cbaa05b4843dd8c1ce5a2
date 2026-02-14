# The Food Collector Truck Mission - Frontend

## Frontend Deployment

**GitHub Pages URL:** https://skill-in-projects.github.io/698cbaa05b4843dd8c1ce5a2/

## Backend API

**API URL:** https://webapi698cbaa05b4843dd8c1ce5a2-production.up.railway.app

## Project Structure

- `index.html` - Main landing page
- `foundations.css` - Design tokens (colors, typography, spacing)
- `style.css` - Global styles
- `config.js` - API configuration

## Design foundations (`foundations.css`)

`foundations.css` defines the project’s **design tokens** so colors, typography, and spacing stay consistent and easy to change in one place.

**How to use the design tokens:**

1. **Load foundations first** – In any page, link `foundations.css` before your other styles so variables are available:
   ```html
   <link rel="stylesheet" href="foundations.css">
   <link rel="stylesheet" href="style.css">
   ```

2. **Use CSS variables in your styles** – Prefer tokens over hardcoded values:
   - **Colors:** `var(--color-primary)`, `var(--color-text-muted)`, `var(--color-success-bg)`, etc.
   - **Typography:** `var(--font-family-sans)`, `var(--text-lg)`, `var(--font-semibold)`, `var(--leading-normal)`
   - **Spacing:** `var(--space-4)`, `var(--space-5)`, `var(--space-8)` (4px base scale)
   - **Layout:** `var(--radius-md)`, `var(--shadow-lg)`, `var(--container-max)`

3. **Keep it consistent** – When adding or updating styles, use these variables instead of new hex codes or pixel values so the design system stays coherent.

## Tech stack audit

The file **`TECH_STACK_AUDIT.md`** documents the project’s tech stack, dependency check, and linting status. It’s useful for onboarding and for understanding what’s in place (e.g. vanilla HTML/CSS/JS, no npm, no linters) and what’s recommended for the future. New developers can read it to get a quick overview of the frontend setup.

## Health check

> **Health check:** Clone and push verified. Keep this line updated when you complete setup or deployment checks so the team has a clear status at a glance.