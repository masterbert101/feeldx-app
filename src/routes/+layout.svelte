<script>
	import Footer from '$lib/Footer.svelte';
	import Header from '$lib/Header.svelte';

	let { children } = $props();
</script>

<main class="container">
	<Header />
	{@render children()}
	<Footer />
</main>

<style>
	.container {
		/* overflow: hidden; */
		position: relative;
		/* background-color: rgb(36, 36, 36); */
	}

	:global(h1, h2, h3, h4, h5, a, span, p) {
		font-family: 'Open Sans', sans-serif;
		font-optical-sizing: auto;
		font-weight: 400;
		font-style: normal;
		color: #2a2f1e;
	}
</style>
