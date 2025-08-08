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
	import { faDesktop } from '@fortawesome/free-solid-svg-icons';

	interface LinkItem {
		href: string;
		text: string;
		icon: IconDefinition;
	}

	const links: LinkItem[] = [
		{
			href: 'https://www.instagram.com/bupin.official/',
			text: 'Instagram',
			icon: faInstagram
		},
		{
			href: 'https://www.tiktok.com/@bupin.official',
			text: 'TikTok',
			icon: faTiktok
		},
		{
			href: 'https://play.google.com/store/apps/details?id=com.mmj.qr_scan&hl=id',
			text: 'Play Store',
			icon: faGooglePlay
		},
		{
			href: 'https://apps.apple.com/id/app/bupin/id6743692469',
			text: 'App Store',
			icon: faApple
		},
		{
			href: 'https://desktop.bupin.id/',
			text: 'Bupin Desktop',
			icon: faDesktop
		}
	];
</script>

<div class="flex flex-col items-center justify-center space-y-3.5">
	<enhanced:img
		src={MascottImage}
		alt="Maskot Bupin"
		loading="eager"
		fetchpriority="high"
		height="500"
		width="500"
		class="mb-2 mt-5 h-52 w-auto md:h-72"
	/>
	<h1 class="text-center text-xl font-semibold md:text-2xl text-gray-800">
		Selamat Datang di Portal Bupin
	</h1>
	<p class="text-sm text-gray-600 md:text-base">
		Email: <a href="mailto:support@bupin.id" class="underline">support@bupin.id</a>
	</p>
</div>

<div class="mt-6 w-full max-w-md space-y-4">
	{#each links as { text, href, icon }}
		<a
			{href}
			target="_blank"
			class="flex items-center justify-center rounded-lg bg-white shadow-md px-6 py-3 text-center text-sm text-gray-800 transition hover:bg-gray-100 md:text-base"
		>
			<Fa {icon} class="mr-2 h-5 w-5" />
			{text}
		</a>
	{/each}
</div>
