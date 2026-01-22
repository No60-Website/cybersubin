<script>
	import Title from '$lib/Components/Title.svelte';
	import Title_wild from '$lib/Components/Title_wild.svelte';
	import HighlightText from '$lib/Components/HighlightText.svelte';
	import { _ } from 'svelte-i18n';
</script>

<div class="relative flex min-h-[80svh] flex-col lg:min-h-[100svh] lg:justify-center">
	<div class="flex flex-col gap-8 bg-black px-6 py-12 text-white md:px-10 md:py-16">
		<div class="grid grid-cols-1 gap-8 lg:grid-cols-[2fr_1fr]">
			<!-- Left Column -->
			<div class="flex flex-col pl-8">
				<Title_wild head={$_('menu.future')} title={$_('future.hero1.title')} color="text-red" />
				<div class="flex-auto"></div>
				<p class="text-sm leading-relaxed">
					<HighlightText text={$_('future.hero1.p1')} highlightColor="#C5A46D" />
				</p>
			</div>

			<!-- Right Column -->
			<div class="space-y-6 pl-8">
				<p class="text-sm leading-relaxed">
					<HighlightText text={$_('future.hero1.p2')} highlightColor="#C5A46D" />
				</p>
				<p class="text-sm leading-relaxed">
					<HighlightText text={$_('future.hero1.p3')} highlightColor="#C5A46D" />
				</p>
				<!-- <a href="https://opencyberdance.pages.dev" class="btn inline-block">Let's Experiment</a> -->
			</div>
		</div>
	</div>
	<img src="/video-player.png" alt="Video Player" class="h-auto w-screen" />
</div>

<div
	class="relative flex min-h-[100svh] w-full flex-col gap-8 bg-black px-6 py-12 text-white md:px-10 md:py-16"
>
	<!-- Top Header with Left and Right Text -->
	<div class="flex justify-between">
		<h2 class={`pl-8 text-3xl font-bold text-red md:w-min md:text-6xl`}>{$_('try')}</h2>
		<h2 class={` text-red md:w-min md:text-3xl`}>No.60</h2>
	</div>

	<!-- Center Content -->
	<div class="flex flex-col items-center gap-6 text-center">
		<p class="text-lg">
			<HighlightText text={$_('future.hub.title')} highlightColor="#E63946" />
		</p>
		<div class="flex gap-4">
			<button
				class="rounded-[20px] border border-[#E63946] px-6 py-2 text-[#E63946] hover:border-[#7B0F12] hover:bg-[#7B0F12] hover:text-black"
			>
				{$_('future.hub.button_signup')}
			</button>
			<button
				class="rounded-[20px] border border-white px-6 py-2 text-white hover:bg-white hover:text-black"
			>
				{$_('future.hub.button_login')}
			</button>
		</div>
	</div>

	<!-- Image -->
	<div class="flex justify-center">
		<img src="/join-hub.png" alt="No.60 Hub Diagram" class="h-auto w-full max-w-lg" />
	</div>
</div>
