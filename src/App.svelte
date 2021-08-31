<script>
	import {
		Distill,
		Title,
		Appendix,
		FrontMatter,
		Article,
		Code,
		Cite,
		Footnote,
		Figure,
		AutoFigureLink,
		CustomFigureLink,
		BlockMath,
		InlineMath,
		Placeholder,
	} from "./components";
</script>

<Distill>
	<Title>
		<h1>Svelte Distill</h1>
		<p>This is the Description</p>
	</Title>

	<FrontMatter
		data={{
			authors: [
				{
					author: "Donald R Bertucci",
					authorURL: "https://www.donnybertucci.com/",
					affiliation: "Earth",
					affiliationURL: "https://en.wikipedia.org/wiki/Earth",
				},
			],
			published: "01/01/1843",
			doi: "Dobby On Ibuprofen",
		}}
	/>

	<Article>
		<p>
			this is the intro, but you can do how you place within the <Code
				>Article</Code
			>. This is a just a <a href="https://svelte.dev/">Svelte</a>ified
			version of the
			<a href="https://github.com/distillpub/template"
				>Distill HTML Template</a
			>.
		</p>
		<p>
			You can cite one <Cite key="distill" />, or multiple references <Cite
				key="bertucci2021donny, distill"
			/>. You can also create a footnote for people to hover over <Footnote
				>Here is a footnote area.</Footnote
			>
		</p>

		<h2>Subtitle h2</h2>
		<p>
			Below I'll show the different component Uses.

			<Figure id="example-1">
				<slot slot="figure">
					<Placeholder />
				</slot>
				<slot slot="caption"
					><AutoFigureLink href="#example-1" />:This is the caption
					for the place holder above.</slot
				>
			</Figure>

			In <AutoFigureLink href="#example-1" /> there is a place holder! I could
			also reference it as <CustomFigureLink href="#example-1"
				>Place Holder</CustomFigureLink
			> if I want don't want to reference it by <AutoFigureLink
				href="#example-1"
			/>. There is nothing else to see here...
		</p>

		<h3>Smaller Sub Title h3</h3>
		<p>
			When I create a new figure, the number will automatically increment!

			<Figure id="example-2">
				<slot slot="figure">
					<div style="display: flex; justify-content: center;">
						<BlockMath
							>{`\\int_1^2 \\int_2^3 \\frac{1}{e ^{-xy}} \\ dx \\ dy`}</BlockMath
						>
					</div>
				</slot>
				<slot slot="caption"
					><AutoFigureLink href="#example-2" />: Here, you can do math
					with LaTeX using the <a href="https://katex.org/">KaTeX</a>
					library. You can also do inline math like <InlineMath
						>\rightarrow \ \ \ 3 \approx \pi \approx e</InlineMath
					></slot
				>
			</Figure>
			In <AutoFigureLink href="#example-2" /> I show that you can do math and
			that the figure label increments.
		</p>
	</Article>

	<Appendix src="bibliography.bib" showHiddenCitations={false}>
		<h3>Acknowledgments</h3>
		<p>Here I can put down Acknowledgments and other stuff!</p>

		<h3>Author Contributions</h3>
		<p>Here I can put the contributions and other stuff!</p>
	</Appendix>
</Distill>
