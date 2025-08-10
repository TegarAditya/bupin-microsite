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

	interface LinkItem {
		href: string;
		text: string;
		icon: IconDefinition;
	}

	const links: LinkItem[] = [
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
			href: 'https://web.bupin.id/',
			text: 'Website Bupin',
			icon: faGlobe
		}
	];
</script>

<div class="w-full">
	<div class="flex max-w-md mx-auto flex-col items-center justify-center space-y-3.5">
		<enhanced:img
			src={MascottImage}
			alt="Maskot Bupin"
			loading="eager"
			fetchpriority="high"
			height="500"
			width="500"
			class="mt-5 mb-2 h-52 w-auto md:h-72"
		/>
		<h1 class="font-display text-center text-2xl font-semibold text-gray-800 md:text-2xl">
			Hai, Sobat Digitalian!
		</h1>

		<p class="text-center text-sm text-gray-600 md:text-base">
			Untuk bantuan atau informasi lebih lanjut, silakan hubungi <a
				href="mailto:support@bupin.id"
				class="font-semibold underline">support@bupin.id</a
			>
		</p>
	</div>

	<div class="mx-auto mt-6 w-full max-w-md space-y-4">
		{#each links as { text, href, icon }}
			<a
				{href}
				target="_blank"
				class="flex items-center justify-center rounded-lg bg-white px-6 py-3 text-center text-gray-800 shadow-md transition hover:bg-gray-100 md:text-base"
			>
				<Fa {icon} class="mr-2 h-5 w-5" />
				<span class="font-display">{text}</span>
			</a>
		{/each}
	</div>
</div>
