<script>
	import { onMount } from "svelte";

	let key = "_";
	export let src = "something.bib";
	onMount(async () => {
		const bib = await fetch(src);
		if (bib.status == 200) {
			const text = await bib.text();
			const matches = text.match(/@article{(.*?),/g);
			const startLength = "@article{".length;

			const stringRefs = matches.map((match) => {
				const endLength = match.length - 1;
				return match.slice(startLength, endLength);
			});
			key = stringRefs;
		}
	});
</script>

<d-cite class="hidden-citations" {key} />

<style>
	.hidden-citations {
		display: none;
	}
</style>
