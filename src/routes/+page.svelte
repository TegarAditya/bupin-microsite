<script lang="ts">
	import MascottImage from '$lib/images/mascott.png?enhanced';

	interface LinkItem {
		href: string;
		text: string;
		icon: string;
	}

	const links: LinkItem[] = [
		{
			href: 'https://www.instagram.com/bupin.official/',
			text: 'Instagram',
			icon: 'fab fa-instagram'
		},
		{
			href: 'https://www.tiktok.com/@bupin.official',
			text: 'TikTok',
			icon: 'fab fa-tiktok'
		},
		{
			href: 'https://play.google.com/store/apps/details?id=com.mmj.qr_scan&hl=id',
			text: 'Bupin Scanner',
			icon: 'fab fa-google-play'
		},
		{
			href: 'https://desktop.bupin.id/',
			text: 'Bupin Desktop',
			icon: 'fas fa-desktop'
		}
	];

	const thisYear = new Date().getFullYear();
</script>

<div class="flex flex-col items-center justify-center space-y-3.5">
	<enhanced:img src={MascottImage} alt="Maskot Bupin" class="mb-4 h-52 w-auto md:h-72" />
	<h1 class="text-center text-2xl font-semibold">Selamat Datang di Portal Bupin</h1>
	<p class="text-gray-400">
		Email: <a href="mailto:support@bupin.id" class="underline">support@bupin.id</a>
	</p>
</div>

<div class="mt-6 w-full max-w-md space-y-4">
	{#each links as { text, href, icon }, i}
		<a
			{href}
			target="_blank"
			class="flex items-center justify-center rounded-lg bg-gray-800 px-6 py-3 text-center text-white transition hover:bg-gray-700"
		>
			<i class="{icon} mr-2"></i>
			{text}
		</a>
	{/each}
</div>

<div class="mt-10 text-xs text-gray-400 md:absolute md:bottom-[15px] md:mt-0">
	&copy; {thisYear} PT Margo Mitro Joyo. All rights reserved.
</div>
