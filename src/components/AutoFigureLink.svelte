<script>
	import { onMount } from "svelte";
	import CustomFigureLink from "./CustomFigureLink.svelte";

	import { dict, currentFigureIndex } from "./figureStore";
	let myIndex = 0;
	export let href = "";
	onMount(() => {
		dict.update((d) => {
			currentFigureIndex.update((count) => {
				myIndex = href in d ? count : count + 1;
				return myIndex;
			});
			return { ...d, [href]: null };
		});
	});
</script>

<CustomFigureLink {href}>Figure {myIndex}</CustomFigureLink>
