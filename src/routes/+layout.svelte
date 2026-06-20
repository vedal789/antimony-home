<script>
	import favicon from '/logo.svg';
	import '$lib/assets/style.css';

	let { children } = $props();
</script>

<svelte:head>
	<title>Antimony - Home</title>
	<link rel="icon" href={favicon} />
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet" />

	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link href="https://fonts.googleapis.com/css2?family=Black+Ops+One&display=swap" rel="stylesheet" />
</svelte:head>

<div class="page">
	{@render children()}
</div>