<script>
	import favicon from '$lib/assets/kay.jpg';
	import '$lib/style.css'

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}
