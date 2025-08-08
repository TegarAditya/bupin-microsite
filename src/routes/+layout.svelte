<script lang="ts">
	import '../app.css';
	import '@fontsource/bricolage-grotesque/400.css';
	import '@fontsource/bricolage-grotesque/600.css';
	import '@fontsource/inter/400.css';
	import '@fontsource/inter/600.css';

	let { children } = $props();

	const thisYear = new Date().getFullYear();
</script>

<svelte:head>
	<meta charset="UTF-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<meta http-equiv="x-ua-compatible" content="IE=7" />
	<meta http-equiv="content-type" content="text/html;charset=UTF-8" />
	<meta name="description" content="Akses berbagai aplikasi Bupin 4.0" />
	<title>Portal Bupin</title>
</svelte:head>

<div class="relative flex min-h-screen flex-col items-center justify-between p-6 text-gray-800 bg-gradient-to-br from-pink-50 via-blue-50 to-purple-50">
	<div class="absolute -z-10 inset-0 bg-[radial-gradient(ellipse_at_center,rgba(255,255,255,0.6)_0%,transparent_70%)] pointer-events-none"></div>
	{@render children()}
	<div class="mt-10 mb-2 text-xs text-gray-500 md:absolute md:bottom-[15px]">
		&copy; {thisYear} PT Margo Mitro Joyo. All rights reserved.
	</div>
</div>
