<script>
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
	export let overrideDOI = false;
	export let override = {
		name: "name",
		innerHTML: "hello!",
	};
</script>

<d-byline>
	<div class="byline grid">
		<div class="authors-affiliations grid">
			<h3>Authors</h3>
			<h3>Affiliations</h3>

			{#each data.authors as entry}
				<p class="author">
					<a class="name" href={entry.authorURL}>{entry.author}</a>
				</p>
				<p class="affiliation">
					<a class="affiliation" href={entry.affiliationURL}
						>{entry.affiliation}</a
					>
				</p>
			{/each}
		</div>
		<div>
			<h3>Published</h3>
			<p>{data.published}</p>
		</div>
		{#if !overrideDOI}
			<div>
				<h3>DOI</h3>
				<p><a href="https://doi.org/{data.doi}">{data.doi}</a></p>
			</div>
		{:else}
			<div>
				<h3>{override.name}</h3>
				<p>{@html override.innerHTML}</p>
			</div>
		{/if}
	</div>
</d-byline>
