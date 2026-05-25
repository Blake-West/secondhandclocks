<svelte:head>
	<title>contact · secondhandclocks</title>
</svelte:head>

<section>
	<h1 class="mb-6 text-4xl md:text-5xl">contact</h1>

	<p class="mb-10 text-lg text-ink-soft">
		If you have a clock joke, a complaint about clock jokes, or a strong opinion about hour hands,
		we'd love to hear it.
	</p>

	<div class="grid gap-4 md:grid-cols-2">
		<!-- TODO: swap with whichever address you actually want public -->
		<a
			href="mailto:hello@secondhandclocks.com"
			class="flex flex-col gap-1 rounded-2xl bg-coral p-6 text-white shadow-sm transition hover:bg-coral-deep hover:shadow-md"
		>
			<span class="text-xs font-bold tracking-widest uppercase opacity-80">email</span>
			<span class="text-xl font-black">hello@secondhandclocks.com</span>
			<span class="text-sm opacity-90">opens your mail client</span>
		</a>

		<a
			href="https://github.com/Blake-West"
			target="_blank"
			rel="noopener noreferrer"
			class="flex flex-col gap-1 rounded-2xl bg-ink p-6 text-white shadow-sm transition hover:bg-ink-soft hover:shadow-md"
		>
			<span class="text-xs font-bold tracking-widest uppercase opacity-80">github</span>
			<span class="text-xl font-black">@Blake-West</span>
			<span class="text-sm opacity-90">code, mostly. some of it works.</span>
		</a>
	</div>

	<p class="mt-10 text-sm text-ink-soft italic">
		A real form (with a real backend) is on the to-do list. Until then, email works fine.
	</p>
</section>
