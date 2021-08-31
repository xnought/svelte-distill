<script>
	export let width = "100%;";
	export let height = 20;
	export let placeholderText = "Place holder";
</script>

<div id="placeholder" style="width: {width}; height: {height}em;">
	<div
		id="placeholder-text"
		style="font-size: {height < 20 ? height / 4 : 4}em;"
	>
		{placeholderText}
	</div>
</div>

<style>
	:root {
		--h: 207;
		--s: 44%;
		--l: 0%;
	}
	#placeholder {
		background-color: hsla(var(--h), var(--s), var(--l), 0.1);
		display: flex;
		justify-content: center;
		align-items: center;
	}
	#placeholder-text {
		color: hsla(var(--h), var(--s), var(--l), 0.5);
		text-transform: uppercase;
	}
</style>
