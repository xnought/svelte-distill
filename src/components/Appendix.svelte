<script>
	import Bibliography from "./Bibliography.svelte";
	import HiddenCitations from "./HiddenCitations.svelte";
	export let src = "bib.bib";
	export let showHiddenCitations = false;
</script>

{#if showHiddenCitations}
	<HiddenCitations {src} />
{/if}

<d-appendix>
	<slot />
	<d-footnote-list />
	<d-citation-list />
</d-appendix>

<Bibliography {src} />
