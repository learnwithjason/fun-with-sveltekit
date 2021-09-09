<script context="module">
	export const prerender = true;
</script>

<script>
	import Boop from '$lib/Boop.svelte';
</script>

<svelte:head>
	<title>Home</title>
</svelte:head>

<section>
	<h1>
		Hello Chat!
	</h1>

	<Boop />
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}

	h1 {
		width: 100%;
	}
</style>
