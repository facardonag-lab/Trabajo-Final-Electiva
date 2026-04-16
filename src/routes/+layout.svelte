<svelte:head>
	<title>Prueba Lectiva</title>
	<meta
		name="description"
		content="Base SvelteKit con arquitectura feature-first/domain-first para integrar Rick and Morty."
	/>
</svelte:head>

<div class="app-shell">
	<slot />
</div>

<style>
	:global(html) {
		color-scheme: light;
	}

	:global(body) {
		margin: 0;
		font-family:
			Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
		background:
			radial-gradient(circle at top, rgba(147, 197, 253, 0.28), transparent 35%),
			linear-gradient(180deg, #dbeafe 0%, #60a5fa 100%);
		color: #0f1c2e;
		min-height: 100vh;
	}

	.app-shell {
		min-height: 100vh;
	}
</style>
