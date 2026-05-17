<script>
	import icons from '$lib/assets/icons.json';

	const quoteSolid = icons['square-quote'].sharp.solid;
	const quoteLight = icons['square-quote'].sharp.regular;
    const hanziSolid = icons['language'].sharp.solid;
</script>

<div class="flex h-dvh w-full flex-col items-center justify-center">
	<ul class="flex flex-col gap-6">
		<li>
			<a
				class="link group opacity-75 duration-300 hocus:opacity-90"
				href="https://ebbmango.github.io/quote-slicer-docs"
			>
				<svg class="h-18 w-18 shrink-0 fill-current" viewBox={quoteSolid['view-box']}>
					{#each quoteSolid.paths as path}
						<path d={path} />
					{/each}
				</svg>
				<div class="link-text duration-300 group-hocus:translate-x-1">
					<span class="uppercase">Quote//Slicer</span>
					<span>Documentation</span>
				</div>
			</a>
		</li>
		<li>
			<div class="link opacity-30">
				<svg class="h-18 w-18 shrink-0 fill-current" viewBox={quoteLight['view-box']}>
					{#each quoteLight.paths as path}
						<path d={path} />
					{/each}
				</svg>
				<div class="link-text">
					<span class="uppercase">Quote//Slicer</span>
					<span>Loading...</span>
				</div>
			</div>
		</li>
        		<li>
			<div class="link opacity-30">
				<svg class="h-18 w-18 shrink-0 fill-current" viewBox={hanziSolid['view-box']}>
					{#each hanziSolid.paths as path}
						<path d={path} />
					{/each}
				</svg>
				<div class="link-text">
					<span class="uppercase">Hanzi//Slicer</span>
					<span>Loading...</span>
				</div>
			</div>
		</li>
	</ul>
</div>

<style lang="postcss">
	@reference './layout.css';

	.link {
		@apply flex items-center gap-2;
	}

	.link-text {
		@apply flex flex-col flex-nowrap font-mono text-nowrap;
	}
</style>
