<script>
	import { PrismicLink } from '@prismicio/svelte';
	import WordMark from './Wordmark.svelte';
	import { field } from 'fp-ts';
	import ButtonLink from './ButtonLink.svelte';

	/** @type {import("@prismicio/client").Content.SettingsDocument}*/
	export let settings;
</script>

<header>
	<nav
		class="flex flex-col items-center justify-between gap-6 border-t border-gray-600 px-6 py-7 md:flex-row"
	>
		<a href="/">
			<WordMark />
			<span class="sr-only">{settings.data.site_title} home page</span>
		</a>

		<ul class="flex items-center gap-8">
			{#each settings.data.navigation as item (item.label)}
				<li>
					{#if item.cta_button}
						<ButtonLink field={item.navigation_link}>{item.label}</ButtonLink>
					{:else}
						<PrismicLink field={item.navigation_link} class="inline-flex min-h-11 items-center">
							{item.label}
						</PrismicLink>
					{/if}
				</li>
			{/each}
		</ul>
	</nav>
</header>
