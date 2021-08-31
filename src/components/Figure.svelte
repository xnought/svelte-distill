<script>
	export let id = "unique";
</script>

<d-figure {id}>
	<figure>
		<slot name="figure" />
		<figcaption>
			<slot name="caption" />
		</figcaption>
	</figure>
</d-figure>

<style>
	d-figure.base-grid {
		grid-column: screen;
		background: hsl(0, 0%, 97%);
		padding: 20px 0;
		border-top: 1px solid rgba(0, 0, 0, 0.1);
		border-bottom: 1px solid rgba(0, 0, 0, 0.1);
	}
	d-figure {
		margin-bottom: 1em;
		position: relative;
	}
	d-figure > figure {
		margin-top: 1em;
		margin-bottom: 1em;
	}
	figcaption {
		margin-top: 1em;
		margin-bottom: 1em;
	}
</style>
