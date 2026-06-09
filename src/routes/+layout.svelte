<script>
	import favicon from '/logo.svg';
	import css from '$lib/assets/style.css';

	let { children } = $props();
</script>

<svelte:head>
	<title>Antimony - Home</title> 
	<link rel="icon" href={favicon} />
	<link rel="stylesheet" href={css} />
</svelte:head>

{@render children()}
