<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
	import Navbar from '$lib/components/Navbar.svelte';

	let { children } = $props();
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<div class="flex min-h-screen flex-col">
	<Navbar />
	<main class="mx-auto w-full max-w-3xl flex-1 px-6 py-12 md:py-20">
		{@render children()}
	</main>
	<footer class="py-6 text-center text-sm text-ink-soft">
		<p>© {new Date().getFullYear()} · the only second that matters</p>
	</footer>
</div>
