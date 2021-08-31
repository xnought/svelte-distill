<script>
	export let href = "";
</script>

<a class="figure-number-text" {href}><slot /></a>

<style>
	a.figure-number {
		border-bottom-color: hsla(206, 90%, 20%, 0.3);
		text-transform: uppercase;
		font-size: 0.85em;
		color: hsla(206, 90%, 20%, 0.7);
	}
	a.figure-number:hover {
		border-bottom-width: 1px;
		border-bottom-style: solid;
		border-bottom-color: hsla(206, 90%, 20%, 0.7);
	}
	a.figure-number-text {
		border-bottom-color: hsla(206, 90%, 20%, 0.3);
		color: hsla(206, 90%, 20%, 0.7);
	}
	a.figure-number-text:hover {
		border-bottom-width: 1px;
		border-bottom-style: solid;
		border-bottom-color: hsla(206, 90%, 20%, 0.7);
	}
</style>
