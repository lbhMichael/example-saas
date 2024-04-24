<script>
	import { PrismicImage, PrismicLink, PrismicRichText, PrismicText } from '@prismicio/svelte';
	/** @type {import("@prismicio/client").Content.HeroSlice} */
	export let slice;
</script>

<section data-slice-type={slice.slice_type} data-slice-variation={slice.variation}>
	<PrismicRichText field={slice.primary.heading} />
	<PrismicRichText field={slice.primary.body} />
	<PrismicLink field={slice.primary.button_link}>
		{slice.primary.label}
	</PrismicLink>
	<PrismicImage field={slice.primary.image}></PrismicImage>
</section>
