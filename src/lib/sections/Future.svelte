<script>
	import { onMount } from 'svelte';
	import Title from '$lib/Components/Title.svelte';
	import Title_wild from '$lib/Components/Title_wild.svelte';
	import HighlightText from '$lib/Components/HighlightText.svelte';
	import { _ } from 'svelte-i18n';

	let parallax = 0;
	let sectionRef;

	onMount(() => {
		const handleScroll = () => {
			if (sectionRef) {
				const rect = sectionRef.getBoundingClientRect();
				// Calculate offset relative to when section enters viewport
				// Offset is 0 when section top is at viewport top
				parallax = -rect.top;
			}
		};

		document.addEventListener('scroll', handleScroll, { passive: true });
		handleScroll(); // Initial call

		return () => {
			document.removeEventListener('scroll', handleScroll);
		};
	});
</script>

<div class="relative flex min-h-[80svh] flex-col p-6 lg:min-h-[100svh] lg:justify-center lg:px-10">
	<div class="flex flex-col gap-8 bg-black text-white md:px-10 md:py-16">
		<!-- Header Section -->
		<Title_wild
			head={$_('menu.future')}
			title={$_('future.hero1.title') + '\n' + $_('future.hero1.title2')}
			color="text-red"
			h4Style="font-family: 'Archivo', 'noto sans thai', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Liberation Sans', sans-serif; md:text-[60px]; font-weight: 400;"
		/>

		<!-- Two Column Layout -->
		<div class="grid grid-cols-1 items-center gap-8 lg:grid-cols-2">
			<!-- Left Column - Text -->
			<div class="space-y-6">
				<p class="text-sm leading-relaxed">
					<HighlightText text={$_('future.hero1.p2')} highlightColor="#C5A46D" />
				</p>
				<p class="text-sm leading-relaxed">
					<HighlightText text={$_('future.hero1.p3')} highlightColor="#C5A46D" />
				</p>
				<p class="text-sm leading-relaxed">
					<HighlightText text={$_('future.hero1.p1')} highlightColor="#C5A46D" />
				</p>
			</div>

			<!-- Right Column - Video/Image -->
			<div class="relative flex items-center justify-center">
				<img src="/video-player.png" alt="Video Player" class="h-auto w-[720px]" />
			</div>
		</div>
	</div>
</div>

<!-- Try it -->
<div
	bind:this={sectionRef}
	class="relative flex min-h-[100svh] w-full flex-col gap-8 bg-black px-6 py-12 text-white md:px-10 md:py-16"
>
	<!-- Top Header with Left and Right Text -->
	<div class="flex items-center justify-between">
		<h2
			class={`font-bold text-[#E63946] md:w-min md:pl-8 md:text-6xl`}
			style="font-family: 'Archivo', 'noto sans thai', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Liberation Sans', sans-serif; font-size: 60px;"
		>
			{$_('try')}
		</h2>
		<h2 class={`text-[36px] text-[#E63946] md:w-min md:text-3xl`}>No.60</h2>
	</div>

	<!-- Center Content -->
	<div class="flex flex-col items-center gap-6 text-center">
		<p
			class="text-[22px]"
			style="font-family: 'Archivo', 'noto sans thai', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Liberation Sans', sans-serif; "
		>
			<HighlightText text={$_('future.hub.title')} highlightColor="#E63946" />
		</p>
		<div
			class="flex flex-col gap-4 md:flex-row"
			style="font-family: 'Archivo', 'noto sans thai', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Liberation Sans', sans-serif;"
		>
			<a
				href="https://learn.pkdance.co/"
				class="rounded-[20px] border border-[#E63946] px-6 py-2 text-[17px] text-[#E63946] hover:border-[#7B0F12] hover:bg-[#7B0F12] hover:text-black"
			>
				{$_('future.hub.button_signup')}
			</a>
			<a
				href="https://learn.pkdance.co/login"
				class="rounded-[20px] border border-white px-6 py-2 text-[17px] text-white hover:bg-white hover:text-black"
			>
				{$_('future.hub.button_login')}
			</a>
		</div>
	</div>
	<!-- Image -->
	<div class="pointer-events-none absolute left-0 top-0 z-0 h-[100svh] w-screen overflow-x-hidden">
		<img
			src="/hero/left-1.png"
			style={`transform: translate3d(0px, ${parallax * 0.08}px, 0px); will-change: transform;`}
			class="absolute -left-[1%] top-[60%] h-72 lg:left-[28%] lg:top-[40%] xl:left-[32%]"
			alt=""
		/>
		<img
			src="/hero/right-1.png"
			style={`transform: translate3d(0px, -${parallax * 0.08}px, 0px); will-change: transform;`}
			class="absolute -right-[11%] top-[70%] h-72 lg:right-[25%] lg:top-[40%] xl:right-[28%]"
			alt=""
		/>
		<img
			src="/hero/left-2.png"
			style={`transform: translate3d(0px, -${parallax * 0.1}px, 0px); will-change: transform;`}
			class="absolute left-[4%] top-[40%] hidden h-72 lg:block xl:left-[8%]"
			alt=""
		/>
		<img
			src="/hero/right-2.png"
			style={`transform: translate3d(0px, ${parallax * 0.1}px, 0px); will-change: transform;`}
			class="absolute right-[2%] top-[40%] hidden h-72 lg:block xl:right-[8%]"
			alt=""
		/>
	</div>
</div>
