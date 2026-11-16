<script lang="ts">
	let { children } = $props();
	import '../app.css';
	import { base } from '$app/paths';
</script>

<svelte:head>
	<link rel="icon" href="{base}/favicon.ico" sizes="32x32 64x64" />
	<link rel="icon" type="image/png" href="{base}/favicon-64.png" sizes="64x64" />
	<link rel="apple-touch-icon" href="{base}/apple-touch-icon.png" sizes="180x180" />
	<title>Anya Aggarwal</title>
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<meta
		name="description"
		content="Student researcher at Under Research Labs. Focus on large language models, agentic reasoning, and verifiable foundation-model systems."
	/>
	<link rel="canonical" href="https://anya-research.github.io/anyaaggarwal/" />

	<meta property="og:type" content="website" />
	<meta property="og:site_name" content="Anya Aggarwal" />
	<meta property="og:title" content="Anya Aggarwal" />
	<meta
		property="og:description"
		content="Student researcher at Under Research Labs. Focus on large language models, agentic reasoning, and verifiable foundation-model systems."
	/>
	<meta property="og:url" content="https://anya-research.github.io/anyaaggarwal/" />
	<meta property="og:image" content="https://anya-research.github.io/anyaaggarwal/og.png" />
	<meta property="og:image:alt" content="Anya Aggarwal's avatar" />
	<meta name="twitter:card" content="summary" />

	<!-- prettier-ignore -->
	<script type="application/ld+json">
		{JSON.stringify({
			'@context': 'https://schema.org',
			'@type': 'Person',
			name: 'Anya Aggarwal',
			url: 'https://anya-research.github.io/anyaaggarwal/',
		})}
	</script>
</svelte:head>

{@render children?.()}
