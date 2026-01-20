<script>
	import Title from '$lib/Components/Title.svelte';
	import Title_wild from '$lib/Components/Title_wild.svelte';
	import HighlightText from '$lib/Components/HighlightText.svelte';
	import { _ } from 'svelte-i18n';
</script>

<div class="relative flex min-h-[80svh] flex-col gap-8 bg-black px-6 py-12 text-white md:px-10 md:py-16 lg:min-h-[100svh] lg:justify-center">
	<div class="grid grid-cols-1 gap-8 lg:grid-cols-[2fr_1fr]">
		<!-- Left Column -->
		<div class="pl-8 flex flex-col">
			<Title_wild head={$_('menu.future')} title="Learning Dance Movements through No. 60 and AI" color="text-red" />
			<div class="flex-auto"></div>
			<p class="text-sm leading-relaxed">
				<HighlightText text={$_('future.hero1.p1')} highlightColor="#C5A46D" />
			</p>
		</div>
	

		<!-- Right Column -->
		<div class="pl-8 space-y-6">
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

<div class="relative h-[100svh] w-full md:pl-10">
	<iframe
		class="h-full w-full"
		src="https://opencyberdance.pages.dev/"
		title="cybersubin"
		frameborder="0"
	></iframe>
	<div class="absolute right-0 top-0 p-3 md:p-6">
		<h2 class={`text-3xl font-bold text-red md:w-min md:text-6xl`}>{$_('try')}</h2>
	</div>
</div>

<div
	class="grid grid-cols-1 bg-neutral-800 pb-12 pt-16 md:ml-10 md:grid-cols-3 lg:min-h-[100svh]"
	id="past-end"
>
	<div class="flex flex-col gap-4 px-6 md:gap-16 lg:px-8">
		<Title head={$_('menu.future')} title="Cyber Subin" color="text-red" />
	</div>
	<div class="mt-6 gap-4 space-y-8 md:col-span-2 md:mt-0">
		<div class="aspect-[21/9] w-full overflow-hidden bg-neutral-600">
			<img src="/cybersubin-2.png" class="center min-h-full min-w-full object-cover" alt="" />
		</div>
		<div class="grid gap-6 px-6 text-white md:pl-0 lg:grid-cols-2 lg:gap-0 lg:px-0">
			<div></div>
			<div class="w-full space-y-6 text-balance lg:w-11/12">
				<p>
					<HighlightText text={$_('future.hero2.p1')} highlightColor="#C5A46D" />
				</p>
			</div>
		</div>
	</div>
</div>
