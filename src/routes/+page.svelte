<script lang="ts">
	import MascottImage from '$lib/images/mascott.png?enhanced';
	import { FontAwesomeIcon as Fa } from '@fortawesome/svelte-fontawesome';
	import {
		faInstagram,
		faTiktok,
		faGooglePlay,
		faApple,
		type IconDefinition
	} from '@fortawesome/free-brands-svg-icons';
	import { faGlobe } from '@fortawesome/free-solid-svg-icons';
	import { onMount } from 'svelte';
	import { animate, press } from 'motion';

	interface LinkItem {
		href: string;
		text: string;
		icon: IconDefinition;
		beat?: boolean;
	}

	const links: LinkItem[] = [
		{
			href: 'https://play.google.com/store/apps/details?id=com.mmj.qr_scan&hl=id',
			text: 'Play Store',
			icon: faGooglePlay,
			beat: false
		},
		{
			href: 'https://apps.apple.com/id/app/bupin/id6743692469',
			text: 'App Store',
			icon: faApple,
			beat: false
		},
		{
			href: 'https://www.instagram.com/bupin.official/',
			text: 'Instagram',
			icon: faInstagram,
			beat: false
		},
		{
			href: 'https://www.tiktok.com/@bupin.official',
			text: 'TikTok',
			icon: faTiktok,
			beat: false
		},
		{
			href: 'https://web.bupin.id/',
			text: 'Website Bupin',
			icon: faGlobe,
			beat: false
		}
	];

	let ready = $state(false);

	onMount(() => {
		ready = true;

		animate(
			'#mascott-image',
			{ scale: [0.5, 1], opacity: [0, 0.5, 1] },
			{ type: 'spring', bounce: 0.6 }
		);

		press('#mascott-image', (el) => {
			animate(el, { scale: [1, 0.8] });
			return () => animate(el, { scale: [0.8, 1] }, { type: 'spring', bounce: 0.6 });
		});

		document.querySelectorAll('.link-item').forEach((el, i) => {
			animate(el, { opacity: [0, 1], transform: ['translateY(10px)', 'translateY(0)'] }, { duration: 0.3 });
		});
	});
</script>

<svelte:head>
	<meta name="description" content="Akses berbagai aplikasi Bupin 4.0" />
	<title>Portal Bupin</title>
	<link rel="canonical" href="https://portal.bupin.id" />
</svelte:head>

<div class="w-full">
	<div class="mx-auto flex max-w-md flex-col items-center justify-center space-y-3.5">
		<div id="mascott-image" class="mt-5 mb-2 h-56 md:h-72" class:invisible={!ready}>
			<enhanced:img
				src={MascottImage}
				alt="Maskot Bupin"
				loading="eager"
				fetchpriority="high"
				height="500"
				width="500"
				class="h-full w-auto"
			/>
		</div>

		<h1 class="font-display text-center text-2xl font-semibold text-gray-800 md:text-2xl">
			Hai, Sobat Digitalian!
		</h1>

		<p class="text-center text-sm text-gray-600 md:text-base">
			Untuk bantuan atau informasi lebih lanjut, silakan hubungi
			<a href="mailto:support@bupin.id" class="font-semibold underline">support@bupin.id</a>
		</p>
	</div>

	<div class="mx-auto mt-6 w-full max-w-md space-y-4">
		{#each links as { text, href, icon, beat }}
			<a
				{href}
				target="_blank"
				class="link-item relative flex h-12 items-center justify-between rounded-lg bg-white p-1 text-center text-gray-800 shadow-md transition hover:bg-gray-100 md:text-base"
			>
				<div class="absolute h-10 rounded-md bg-gray-100">
					<Fa {icon} class="h-5 w-5 p-3" {beat} size="1x" />
				</div>
				<div class="w-full">
					<span class="font-display">{text}</span>
				</div>
			</a>
		{/each}
	</div>
</div>
