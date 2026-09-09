<script>
	import icons from '$lib/assets/icons.json';

	const quoteSolid = icons['square-quote'].sharp.solid;
	const quoteLight = icons['square-quote'].sharp.regular;
	const hanziSolid = icons['language'].sharp.solid;
	const verbariumSolid = icons['graduation-cap'].sharp.solid;

	let visibleDots = $state(0);

	$effect(() => {
		const interval = setInterval(() => {
			visibleDots = (visibleDots + 1) % 4;
		}, 1000);

		return () => clearInterval(interval);
	});
</script>

<div class="flex h-dvh w-full flex-col items-center justify-center">
	<ul class="flex flex-col gap-6">
	<!-- Quote Slicer -->
		<li>
			<a
				class="link group opacity-75 duration-300 hocus:opacity-90"
				href="https://ebbmango.github.io/quote-slicer"
			>
				<svg class="h-18 w-18 shrink-0 fill-current" viewBox={quoteLight['view-box']}>
					{#each quoteLight.paths as path}
						<path d={path} />
					{/each}
				</svg>
				<div class="link-text duration-300 group-hocus:translate-x-1">
					<span class="uppercase">Quote//Slicer</span>
					<span class="opacity-50">MVP is live now! 🎉</span>
				</div>
			</a>
		</li>
		<!-- Quote Slicer Docs -->
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
		<!-- Hanzi Slicer -->
		<li>
			<div class="link opacity-30">
				<svg class="h-18 w-18 shrink-0 fill-current" viewBox={hanziSolid['view-box']}>
					{#each hanziSolid.paths as path}
						<path d={path} />
					{/each}
				</svg>
				<div class="link-text">
					<span class="uppercase">Hanzi//Slicer</span>
					<span>Planning phase<span aria-hidden="true">{#each [1, 2, 3] as dot}<span class:invisible={dot > visibleDots}>.</span>{/each}</span>✏️</span>
				</div>
			</div>
		</li>
		<!-- Verbarium -->
		<li>
			<a
				class="link group opacity-75 duration-300 hocus:opacity-90"
				href="https://ebbmango.github.io/verbarium"
			>
				<svg class="h-18 w-18 shrink-0 fill-current" viewBox={verbariumSolid['view-box']}>
					{#each verbariumSolid.paths as path}
						<path d={path} />
					{/each}
				</svg>
				<div class="link-text duration-300 group-hocus:translate-x-1">
					<span class="uppercase">Verbarium</span>
					<span class="opacity-50">Work in Progress 🚧</span>
				</div>
			</a>
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
