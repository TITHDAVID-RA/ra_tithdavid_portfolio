# Ra Tithdavid — Portfolio

A personal portfolio site built with Vue 3 + Vite, styled around a
"Frappe DocType record" theme — work experience and education are laid
out like the document records the site owner builds at his day job,
with a terminal-style hero intro.

## Project structure

```
tithdavid-portfolio/
├── index.html              # HTML entry point
├── package.json
├── vite.config.js
├── src/
│   ├── main.js              # Vue app bootstrap
│   ├── App.vue               # Root component, assembles sections
│   ├── style.css             # Design tokens (colors, type) + shared styles
│   ├── assets/
│   │   └── david.jpg         # Profile photo
│   └── components/
│       ├── NavBar.vue
│       ├── Hero.vue          # Terminal intro + photo
│       ├── About.vue
│       ├── Experience.vue    # DocType-style record cards
│       ├── Education.vue
│       ├── Skills.vue
│       ├── Contact.vue
│       └── AppFooter.vue
```

## Run it locally

You'll need [Node.js](https://nodejs.org) (18+) installed.

```bash
# 1. Install dependencies
npm install

# 2. Start the dev server (hot reload)
npm run dev

# 3. Open the URL it prints (usually http://localhost:5173)
```

## Build for production / deploy

```bash
npm run build
```

This outputs a static `dist/` folder you can deploy anywhere — GitHub
Pages, Netlify, Vercel, or any static host.

To deploy on **GitHub Pages**:
1. Push this folder to a GitHub repo.
2. Run `npm run build`.
3. Publish the `dist/` folder to the `gh-pages` branch (or use a GitHub
   Action / the `gh-pages` npm package).

## Editing content

- **Photo**: replace `src/assets/david.jpg` with a new image (keep the
  same filename, or update the import in `src/components/Hero.vue`).
- **Experience / Education / Skills**: edit the arrays at the top of
  `src/components/Experience.vue`, `Education.vue`, and `Skills.vue`.
- **Colors / fonts**: all design tokens live at the top of
  `src/style.css` under `:root`.

## Responsiveness

The layout is fully responsive: the hero photo and terminal stack
vertically below ~720px, record fields stack below ~560px, and nav
links/buttons shrink on small phones.
