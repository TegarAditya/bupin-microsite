<script lang="ts">
	import '../app.css';
	let { children } = $props();
</script>

<svelte:head>
	<meta charset="UTF-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<meta http-equiv="x-ua-compatible" content="IE=7" />
	<meta http-equiv="content-type" content="text/html;charset=UTF-8" />
	<meta name="description" content="Akses berbagai aplikasi Bupin 4.0" />
	<title>Portal Bupin</title>
	<link rel="preconnect" href="https://fonts.googleapis.com" />
	<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin="anonymous" />
	<link
		href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300..700&display=swap"
		rel="stylesheet"
	/>
	<script
		src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.2/js/all.min.js"
		defer
	></script>
</svelte:head>

<div class="flex min-h-screen flex-col items-center justify-center bg-gray-900 p-6 text-white">
	{@render children()}
</div>

<style>
	:global(body) {
		font-family: 'Space Grotesk', sans-serif;
	}
</style>
