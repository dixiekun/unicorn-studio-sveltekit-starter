<script lang="ts">
	import '../app.css';
	
	let { children } = $props();
</script>

<svelte:head>
  <title>Unicorn Studio Showcase</title>
  <meta name="description" content="Showcase of interactive works created with Unicorn Studio, embedded in a SvelteKit app." />
</svelte:head>

{@render children()}
