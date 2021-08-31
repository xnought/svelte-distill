<script>
	import { onMount } from "svelte";

	export let data = {
		authors: [
			{
				author: "...",
				authorURL: "...",
				affiliation: "...",
				affiliationURL: "...",
			},
		],
		published: "01/01/01",
		doi: "Dobby On Ibuprofen",
	};

	function compose(data) {
		return JSON.stringify(data, null, 4);
	}
	let container;
	onMount(() => {
		let script = document.createElement("script");
		script.type = "text/json";
		let frontMatter = document.createElement("d-front-matter");
		const by = document.createElement("d-byline");

		script.innerHTML = compose(data);
		frontMatter.appendChild(script);
		container.appendChild(frontMatter);
		container.appendChild(by);
	});
</script>

<div bind:this={container} />
