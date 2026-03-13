<script>
	import { onMount } from 'svelte';
	import { locale, _ } from 'svelte-i18n';

	let parallax = 0;
	let isIOS = false;

	onMount(() => {
		// Detect touch devices (iOS, Android tablets, etc.)
		// Modern iPads report as "Macintosh" in desktop mode, so we check for touch capability
		isIOS = 'ontouchstart' in window || navigator.maxTouchPoints > 0;

		document.addEventListener('scroll', () => {
			parallax = window.scrollY;
		});
	});
</script>

<div
	class="hero-bg flex h-[100svh] flex-col text-white"
	class:ios-device={isIOS}
	style="font-family: 'Archivo', 'noto sans thai', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Liberation Sans', sans-serif; background-image: url('/hero/hero_bg.png'); background-size: cover; background-position: center;"
>
	<nav
		class="z-20 w-full border-b border-y-white bg-black text-center text-[10px] font-bold md:sm:text-[16px]"
	>
		<div class="divide-x-white z-50 grid w-full grid-cols-3 divide-x [&>a]:p-2">
			<a href="#past" class="hover:cursor-pointer hover:bg-[#C5A46D]">{$_('menu.past')}</a>
			<a href="#present" class="hover:cursor-pointer hover:bg-[#CA6C37]">{$_('menu.present')}</a>
			<a href="#future" class="hover:cursor-pointer hover:bg-[#7B0F12]">{$_('menu.future')}</a>
			{#if false}
			<a
				href="https://learn.pkdance.co/"
				target="_blank"
				rel="noopener noreferrer"
				class="hover:cursor-pointer hover:bg-[#262626]">{$_('menu.login')}</a
			>
			{/if}
		</div>
	</nav>
	<div
		class="flex h-full flex-col justify-center gap-4 p-6 text-center md:items-center md:justify-center md:text-left"
	>
		<div>
			<div class="text-[72px] font-bold leading-none sm:text-8xl md:mt-0">
				<h1>No.60</h1>
			</div>
		</div>
		<p class="text-[13px] text-[#C5A46D] md:max-w-lg md:text-center md:text-xl">
			{$_('hero.description_line1')}
		</p>
	</div>

	<div class="absolute bottom-0 right-0 p-4 md:p-6">
		<div class="divide-x-white flex rounded-full text-lg md:text-xl">
			<button
				on:click={() => {
					locale.set('en');
					sessionStorage.setItem('lang', 'en');
				}}
				class="rounded-l-full border border-r-[0.5px] border-white px-3 hover:bg-white hover:text-black"
			>
				a
			</button>
			<button
				on:click={() => {
					locale.set('th');
					sessionStorage.setItem('lang', 'th');
				}}
				class="rounded-r-full border border-l-[0.5px] border-white px-3 hover:bg-white hover:text-black"
			>
				ก
			</button>
		</div>
	</div>
</div>

<style>
	/* Apply fixed background to ALL devices except iOS */
	.hero-bg:not(.ios-device) {
		background-attachment: fixed;
	}
</style>
