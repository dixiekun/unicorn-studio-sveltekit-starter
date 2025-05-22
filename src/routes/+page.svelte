<script lang="ts">
  // No Svelte state needed for static embed
  // The script will be loaded in onMount
  import { onMount } from 'svelte';

  onMount(() => {
    // Load the UnicornStudio.js script dynamically
    if (!window.UnicornStudio) {
      const script = document.createElement('script');
      script.src = 'https://cdn.jsdelivr.net/gh/hiunicornstudio/unicornstudio.js@v1.4.20/dist/unicornStudio.umd.js';
      script.onload = () => {
        window.UnicornStudio.addScene({
          elementId: 'unicorn-hero',
          filePath: '/unicorn-studio/De_becker_code_hero.json',
          scale: 1,
          dpi: 1.5,
          altText: 'De Becker Code Hero Scene',
          ariaLabel: 'Unicorn Studio Hero Scene',
          production: false,
        });
      };
      document.head.appendChild(script);
    } else {
      window.UnicornStudio.addScene({
        elementId: 'unicorn-hero',
        filePath: '/unicorn-studio/De_becker_code_hero.json',
        scale: 1,
        dpi: 1.5,
        altText: 'De Becker Code Hero Scene',
        ariaLabel: 'Unicorn Studio Hero Scene',
        production: false,
      });
    }
  });
</script>


<div id="unicorn-hero" style="width: 100%; min-height: 900px; background: #f9f6e4; border-radius: 1rem; box-shadow: 0 2px 16px #0001;"></div>
