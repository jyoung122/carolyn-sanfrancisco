<script lang="ts">
	import { PUBLIC_PLAUSIBLE_DOMAIN } from '$env/static/public';
	import type { Locales } from '$i18n/i18n-types';
	import { playerStore, applyLocale } from '$lib/player';
	import { onMount } from 'svelte';
	import { detectLocale, navigatorDetector } from 'typesafe-i18n/detectors';

	onMount(() => {
		const locale: Locales =
			$playerStore?.locale ?? detectLocale('en', ['en'], navigatorDetector);
		applyLocale(locale, playerStore);
	});
</script>

<svelte:head>
	<!-- Primary Meta Tags -->
	<title
		>Carolyn San Diego: Happy Birthday to my lovely wife.</title
	>
	<meta
		name="title"
		content="Carolyn San Diego: Happy Birthday to my lovely wife."
	/>
	<meta
		name="description"
		content="Chase The Bootleggers and his accomplices across different countries, unraveling clues, solving puzzles, and expanding your geography knowledge in this exciting detective game."
	/>

</svelte:head>

<div class="layout">
	<slot />
</div>

<style lang="scss">
	:global(body) {
		--color-neutral-50: #ffffff;
		--color-neutral-100: #e3e8e6;
		--color-neutral-200: #a4b0ac;
		--color-neutral-300: #6d7471;
		--color-neutral-400: #4f5452;
		--color-neutral-500: #3b3f3e;
		--color-neutral-600: #232424;
		--color-neutral-700: #1e1e1e;
		--color-neutral-800: #181818;
		--color-neutral-900: #141414;
		--color-neutral-950: #0f0f0f;
		--color-neutral-1000: #000;

		--color-accent: #0bbc79;
		--color-danger: #ea2c2c;
		--color-capture: #1566b1;

		--border-radius-l: 8px;
		--border-radius-m: 6px;
		--border-radius-s: 4px;

		--spacing-xl: 40px;
		--spacing-l: 20px;
		--spacing-m: 8px;
		--spacing-s: 4px;

		--font-family-sans: 'Inter', sans-serif;
		--font-family-sans-light: 200;
		--font-family-sans-regular: 300;
		--font-family-sans-bold: 700;

		--font-family-mono: 'JetBrains Mono', monospace;
		--font-family-mono-regular: 200;
		--font-family-mono-bold: 700;

		font-family: var(--font-family-sans);
		margin: unset;
		color: var(--color-neutral-100);
		background-color: var(--color-neutral-1000);

		display: flex;
		align-items: center;
		justify-content: center;
		width: 100dvw;
		min-width: 320px;
		height: 100dvh;
	}

	div.layout {
		width: 100dvw;
		min-width: 320px;
		max-width: 512px;

		--layout-inline: 40px;
		--layout-block: 48px;

		height: 100dvh;
		max-height: 1024px;

		@media (max-width: 512px) {
			--layout-inline: 24px;
			--layout-block: 32px;
		}
	}
</style>
