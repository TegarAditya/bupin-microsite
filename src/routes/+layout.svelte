<script lang="ts">
	import '../app.css';
	import '@fontsource/bricolage-grotesque/400.css';
	import '@fontsource/bricolage-grotesque/600.css';
	import '@fontsource/inter/400.css';
	import '@fontsource/inter/600.css';
	import BricolageGrotesque400 from '@fontsource/bricolage-grotesque/files/bricolage-grotesque-latin-400-normal.woff2?url'
	import BricolageGrotesque600 from '@fontsource/bricolage-grotesque/files/bricolage-grotesque-latin-600-normal.woff2?url'
	import Inter400 from '@fontsource/inter/files/inter-latin-400-normal.woff2?url'
	import Inter600 from '@fontsource/inter/files/inter-latin-600-normal.woff2?url'

	let { children } = $props();

	const thisYear = new Date().getFullYear();
</script>

<svelte:head>
	<meta charset="UTF-8" />
	<meta name="viewport" content="width=device-width, initial-scale=1.0" />
	<meta http-equiv="x-ua-compatible" content="IE=7" />
	<meta http-equiv="content-type" content="text/html;charset=UTF-8" />
	<link rel="preload" as="font" type="font/woff2" href={BricolageGrotesque400} crossorigin="anonymous" />
	<link rel="preload" as="font" type="font/woff2" href={BricolageGrotesque600} crossorigin="anonymous" />
	<link rel="preload" as="font" type="font/woff2" href={Inter400} crossorigin="anonymous" />
	<link rel="preload" as="font" type="font/woff2" href={Inter600} crossorigin="anonymous" />
</svelte:head>

<div class="relative min-h-dvh flex flex-col items-center justify-between px-6 text-gray-800 bg-gradient-to-br from-pink-50 via-blue-50 to-purple-50">
	<div class="absolute -z-10 inset-0 bg-[radial-gradient(ellipse_at_center,rgba(255,255,255,0.6)_0%,transparent_70%)] pointer-events-none"></div>
	<div class="block"></div>
	{@render children()}
	<div class="mt-10 mb-7 text-sm text-gray-500">
		&copy; {thisYear} <a href="https://mmj.co.id" target="_blank" class="hover:underline">PT Margo Mitro Joyo</a>.
	</div>
</div>
