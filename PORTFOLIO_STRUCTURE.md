# Portfolio Project Structure & Usage Guide

This document explains the structure and dynamic features of your portfolio project. Use it for future reference and updates.

---

## Directory Overview

- **public/**
  - `projects.json` — All project cards are loaded from here. Add new projects to this file.
  - `certificates.json` — All certificate cards are loaded from here. Add new certificates to this file.
  - `images/` — Store all images used in your portfolio (profile, project images, etc.).
  - `pdf/` — Store your resume PDF.

- **docs/**
  - This is the only build output folder used for deployment (GitHub Pages serves from here).
  - After running the build command, all static assets and built files are copied here.
  - **Delete any old `build/` folder. Only `docs/` is needed.**

- **src/components/**
  - `Projects.tsx` — Renders project cards dynamically from `projects.json`. Shows 3 cards per slide, fills with "Coming Soon" placeholders if needed.
  - `Certificates.tsx` — Renders certificate cards dynamically from `certificates.json`. Always shows 2 cards per row, fills with "Coming Soon" placeholders if needed.
  - `Contact.tsx` — Contact form. To make it work live, connect to a backend or use a service (Formspree, EmailJS, etc.).
  - Other components: `About.tsx`, `Skills.tsx`, `Experience.tsx`, `Footer.tsx`, etc.

- **src/assets/**
  - Store additional images or assets here.

- **src/styles/**
  - Custom CSS files.

---

## Dynamic Content

- **Projects:**
  - Add new projects to `public/projects.json`.
  - Each project card is generated automatically.
  - "Coming Soon" cards fill empty slots.
  - **Image paths in JSON should be relative (e.g., `images/project1.png`).**
  - In code, always use `src={\`${import.meta.env.BASE_URL}${project.image}\`}` for images.

- **Certificates:**
  - Add new certificates to `public/certificates.json`.
  - Each certificate card is generated automatically.
  - "Coming Soon" cards fill empty slots in each row.

---

## Deployment

- Use GitHub Pages for static hosting.
- All data is loaded from static JSON files.
- No backend required unless you want a working contact form.
- **Vite config must use:**
  - `base: '/portfolio/'`
  - `build.outDir: 'docs'`
- **Deploy only the `docs` folder.**

---

## Updating Portfolio

- To add a new project: Edit `public/projects.json`.
- To add a new certificate: Edit `public/certificates.json`.
- To update images: Add to `public/images/` and reference in JSON (no leading slash).
- To update resume: Replace `public/pdf/resume.pdf`.

---

## Notes

- Unused files and Figma references have been removed for a clean repo.
- All cards and sections are responsive and dynamic.
- For a working contact form, connect to a backend or use a third-party service.
- **The `build` folder is not used and can be deleted.**
- **Always use relative asset paths and `import.meta.env.BASE_URL` for compatibility with both local and GitHub Pages deployments.**

---

**This file is your future guide for maintaining and updating your portfolio!**
