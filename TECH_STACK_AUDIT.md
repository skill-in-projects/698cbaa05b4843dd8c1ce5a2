# Tech Stack Audit – Frontend

**Project:** The Food Collector Truck Mission – Frontend  
**Audit date:** 2026-02-14

---

## 1. Tech stack

This repo is **not** a React, Next.js, or other JS framework app. It is a **vanilla frontend**:

| Layer      | Technology        | Evidence |
|-----------|-------------------|----------|
| **Markup** | HTML5             | Single `index.html`, no JSX/TSX |
| **Styles** | CSS               | `style.css` + inline `<style>` in `index.html` |
| **Scripts**| Vanilla JavaScript| `config.js` + inline `<script>` in `index.html`, no bundler |
| **Runtime**| Browser only      | No Node.js, no build step |

**Conclusion:** No React/Next.js/Vue etc. No `package.json`, no npm/yarn/pnpm.

---

## 2. Dependencies

### 2.1 NPM / Node dependencies

| Check              | Status | Notes |
|--------------------|--------|--------|
| `package.json`     | ❌ Missing | No Node/npm project |
| `node_modules`     | N/A    | Not applicable |
| Lock file          | N/A    | No package manager |

**Conclusion:** There are **no npm dependencies** to install or verify. The app runs by opening `index.html` in a browser (or via a static host like GitHub Pages).

### 2.2 External references

| Resource   | Where used      | Purpose |
|-----------|------------------|---------|
| Backend API | `config.js` → `CONFIG.API_URL` | `https://webapi698cbaa05b4843dd8c1ce5a2-production.up.railway.app` |
| Mentor API | `config.js` (tracking) | `https://dev.skill-in.com` for success/error logging |

No CDN scripts or stylesheets are used; all code is local.

---

## 3. Linting and code quality

| Tool / config           | Status | Notes |
|-------------------------|--------|--------|
| ESLint                  | ❌ Not present | No `.eslintrc*`, no `eslint` in scripts |
| Prettier                | ❌ Not present | No `.prettierrc*`, no `prettier` config |
| TypeScript              | ❌ Not used    | No `.ts`/`.tsx`, no `tsconfig.json` |
| Other linters/formatters| ❌ None       | No config files found |

**Conclusion:** **No linting or formatting rules are installed or configured.** Code style is not enforced by tooling.

---

## 4. Repo structure (relevant to frontend)

```
Frontend/
├── .github/workflows/deploy-frontend.yml   # GitHub Pages deploy on push to main
├── .gitignore                              # VS / .NET oriented; includes .env, .vs/, .idea/
├── config.js                               # API URL + mentor tracking
├── index.html                              # Main page (markup + inline CSS/JS)
├── README.md                               # Project info + URLs
└── style.css                               # Global styles
```

Deploy workflow triggers on changes to `index.html`, `config.js`, `style.css`, `frontend/**`, or the workflow file; no build step.

---

## 5. Summary

| Area           | Status | Summary |
|----------------|--------|---------|
| **Stack**      | ✅ Clear | Vanilla HTML + CSS + JS; no framework. |
| **Dependencies** | ✅ N/A | No package manager; nothing to install for current setup. |
| **Linting**    | ❌ Missing | No ESLint, Prettier, or other lint/format rules. |

---

## 6. Recommendations

If you want to align this repo with “dependencies + linting” expectations (e.g. for a course or platform that assumes a Node/React-style project):

1. **Add a minimal Node/npm setup**  
   - `npm init -y`  
   - Add scripts for local preview (e.g. `npx serve .` or a simple static server).

2. **Add linting for JS and HTML**  
   - ESLint for `config.js` and inline JS (with a parser that can handle script tags if needed, or extract JS for linting).  
   - Optionally Prettier for JS/CSS/HTML and an ESLint config that works with Prettier.

3. **Optional: HTML/CSS linting**  
   - e.g. `htmlhint`, `stylelint` via npm scripts and CI.

4. **Keep current setup**  
   - If the project is meant to stay vanilla and deploy as static files only, the current setup is consistent; you can note in the mission that “no npm dependencies or linting are present by design.”

---

*End of audit.*
