# Project Overview: Unicorn Studio Showcase (SvelteKit)

## Description
This project is a SvelteKit web application designed to showcase interactive works created with [Unicorn Studio](https://github.com/hiunicornstudio/unicornstudio.js/tree/v1.4.20). It demonstrates how to embed and display Unicorn Studio scenes using the official UnicornStudio.js SDK via CDN, following the latest Svelte and SvelteKit best practices.

## Features
- SvelteKit-based SPA for modern, fast, and maintainable UI
- Embeds Unicorn Studio scenes dynamically using the UnicornStudio.js CDN
- Showcases sample work: `De_becker_code_hero.json`
- Responsive and accessible scene container
- Easily extensible to add more Unicorn Studio works

## How it works
- The main page loads the UnicornStudio.js script from CDN on mount
- The scene is rendered into a dedicated container using the dynamic `addScene` API
- The scene JSON is referenced from the `/unicorn-studio/De_becker_code_hero.json` file in the public directory

## Database Schema
This project does **not** use a database. All scene data is stored as static JSON files in the `unicorn-studio/` directory.

## File Structure
- `src/routes/+page.svelte`: Main showcase page, loads and displays the Unicorn Studio scene
- `unicorn-studio/De_becker_code_hero.json`: Sample Unicorn Studio scene JSON
- `project-overview.md`: This documentation file

## Adding More Scenes
To add more Unicorn Studio works:
1. Export your scene JSON from Unicorn Studio
2. Place it in the `unicorn-studio/` directory
3. Add a new container and call `UnicornStudio.addScene` in your Svelte page/component

---
_Last updated: Initial setup with De_becker_code_hero.json sample_
