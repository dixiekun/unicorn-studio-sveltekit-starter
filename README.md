# Unicorn Studio SvelteKit Starter

A modern SvelteKit starter template for previewing [Unicorn Studio](https://github.com/hiunicornstudio/unicornstudio.js) animation projects.

- **Live repo:** [github.com/dixiekun/unicorn-studio-sveltekit-starter](https://github.com/dixiekun/unicorn-studio-sveltekit-starter)
- **Powered by:** [SvelteKit](https://kit.svelte.dev/) & [UnicornStudio.js](https://github.com/hiunicornstudio/unicornstudio.js)

---

## Features
- Plug-and-play preview for your Unicorn Studio exported scenes
- Uses UnicornStudio.js via CDN for zero-config embedding
- Example scene included: `De_becker_code_hero.json`
- Clean, responsive, and accessible UI
- Easily extensible for multiple scenes or a gallery

---

## Getting Started

1. **Clone this repo:**
   ```sh
   git clone https://github.com/dixiekun/unicorn-studio-sveltekit-starter.git
   cd unicorn-studio-sveltekit-starter
   ```
2. **Install dependencies:**
   ```sh
   npm install
   ```
3. **Run the dev server:**
   ```sh
   npm run dev -- --open
   ```
4. **Preview your Unicorn Studio scene!**
   - The sample scene is loaded from `/static/unicorn-studio/De_becker_code_hero.json`.
   - Open [http://localhost:5173/](http://localhost:5173/) to view.

---

## Adding Your Own Scenes
1. **Export your scene** from [Unicorn Studio](https://unicorn.studio/) as a JSON file.
2. **Place the file** in `static/unicorn-studio/` (e.g., `static/unicorn-studio/my_scene.json`).
3. **Edit `src/routes/+page.svelte`** to reference your new file:
   ```js
   filePath: '/unicorn-studio/my_scene.json',
   ```
4. **Restart the dev server** if needed, and your new scene will appear!

---

## Project Structure
- `src/routes/+page.svelte` — Main page, loads and displays the Unicorn Studio scene
- `static/unicorn-studio/` — Place your exported scene JSON files here
- `project-overview.md` — Project documentation

---

## Credits
- [Unicorn Studio](https://unicorn.studio/) for the animation platform and SDK
- [SvelteKit](https://kit.svelte.dev/) for the web framework

---

## License
This starter is provided for personal and educational use. See [Unicorn Studio's license](https://github.com/hiunicornstudio/unicornstudio.js/blob/v1.4.20/README.md) for SDK usage terms.
