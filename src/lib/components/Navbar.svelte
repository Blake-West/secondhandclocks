<script lang="ts">
	import { page } from '$app/state';
	import { resolve } from '$app/paths';

	const links = [
		{ href: '/', label: 'home' },
		{ href: '/about', label: 'about' },
		{ href: '/contact', label: 'contact' }
	] as const;

	let menuOpen = $state(false);

	function isActive(href: string) {
		return page.url.pathname === href;
	}
</script>

<nav class="border-b-2 border-coral/30 bg-peach/60 backdrop-blur">
	<div class="mx-auto flex max-w-3xl items-center justify-between px-6 py-4">
		<a
			href={resolve('/')}
			onclick={() => (menuOpen = false)}
			class="flex items-center gap-2 text-xl font-black tracking-tight text-ink transition-colors hover:text-coral-deep"
		>
			<svg
				aria-hidden="true"
				viewBox="0 0 64 64"
				class="h-6 w-6"
				fill="none"
				stroke="currentColor"
				stroke-width="4"
				stroke-linecap="round"
			>
				<circle cx="32" cy="32" r="28" />
				<line x1="32" y1="8" x2="32" y2="14" />
				<line x1="32" y1="56" x2="32" y2="50" />
				<line x1="8" y1="32" x2="14" y2="32" />
				<line x1="56" y1="32" x2="50" y2="32" />
				<line x1="32" y1="32" x2="51" y2="21" class="text-coral-deep" stroke="currentColor" />
				<circle cx="32" cy="32" r="2.5" fill="currentColor" stroke="none" class="text-coral-deep" />
			</svg>
			<span>secondhandclocks</span>
		</a>

		<ul class="hidden gap-7 md:flex">
			{#each links as { href, label } (href)}
				<li>
					<a
						href={resolve(href)}
						class="text-base font-bold transition-colors {isActive(href)
							? 'text-coral-deep underline decoration-coral decoration-2 underline-offset-4'
							: 'text-ink-soft hover:text-coral-deep'}"
					>
						{label}
					</a>
				</li>
			{/each}
		</ul>

		<button
			type="button"
			aria-label="Toggle menu"
			aria-expanded={menuOpen}
			onclick={() => (menuOpen = !menuOpen)}
			class="cursor-pointer text-2xl text-ink hover:text-coral-deep md:hidden"
		>
			{menuOpen ? '✕' : '☰'}
		</button>
	</div>

	{#if menuOpen}
		<ul class="mx-auto flex max-w-3xl flex-col gap-3 border-t border-coral/20 px-6 py-4 md:hidden">
			{#each links as { href, label } (href)}
				<li>
					<a
						href={resolve(href)}
						onclick={() => (menuOpen = false)}
						class="block py-1 text-lg font-bold {isActive(href)
							? 'text-coral-deep'
							: 'text-ink-soft'}"
					>
						{label}
					</a>
				</li>
			{/each}
		</ul>
	{/if}
</nav>
