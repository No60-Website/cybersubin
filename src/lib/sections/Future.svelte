<script>
	import { onMount } from 'svelte';
	import Title from '$lib/Components/Title.svelte';
	import Title_wild from '$lib/Components/Title_wild.svelte';
	import HighlightText from '$lib/Components/HighlightText.svelte';
	import { locale, _ } from 'svelte-i18n';

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

<div
	class="relative flex min-h-[80svh] flex-col overflow-hidden p-6 lg:min-h-[100svh] lg:justify-center lg:px-10"
>
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
			<div class="h-full space-y-6 pt-[20px]">
				<p class="leading-relaxed">
					<HighlightText text={$_('future.hero1.p2')} highlightColor="#C5A46D" />
				</p>
				<p class="leading-relaxed">
					<HighlightText text={$_('future.hero1.p3')} highlightColor="#C5A46D" />
				</p>
				<p class="leading-relaxed">
					<HighlightText text={$_('future.hero1.p1')} highlightColor="#C5A46D" />
				</p>
			</div>

			<!-- Right Column - Subscribe -->
			<div
				bind:this={sectionRef}
				class="relative flex h-full min-h-[400px] flex-col items-center gap-4"
			>
				<img
					src="/hero/left-1.png"
					style={`transform: translate3d(0px, ${parallax * 0.05}px, 0px); will-change: transform;`}
					class="absolute -left-[5%] top-[23%] h-72 lg:left-[28%] lg:top-[10%] xl:left-[10%]"
					alt=""
				/>
				<img
					src="/hero/right-1.png"
					style={`transform: translate3d(0px, -${parallax * 0.05}px, 0px); will-change: transform;`}
					class="absolute -right-[20%] top-[33%] h-72 lg:right-[25%] lg:top-[20%] xl:right-[10%]"
					alt=""
				/>
				<h3 class="text-center text-[28px] text-white md:text-[32px]">
					{$_('future.subscribe.title')}
				</h3>
				<a
					href="https://pkdance.co/?ff_landing=11"
					target="_blank"
					rel="noopener noreferrer"
					class="rounded-[30px] bg-[#7B0F12] px-20 py-3 text-white transition hover:bg-[#9B1F22]"
				>
					{$_('future.subscribe.button')}
				</a>
			</div>
		</div>
	</div>
</div>

<!-- Try it -->
{#if false}
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
		<div
			class="pointer-events-none absolute left-0 top-0 z-0 h-[100svh] w-screen overflow-x-hidden"
		>
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
{/if}

<div
	class="grid items-center bg-gradient-to-b from-[#0000005b] to-[#5252525b] pb-12 pt-16 text-white md:ml-10 md:min-h-[100svh] md:grid-cols-3 md:items-start"
>
	{#if $locale === 'th'}
		<div class="flex flex-col items-center md:w-11/12 md:items-start md:pl-12">
			<div class="mb-6 flex flex-col items-center md:items-start">
				<img
					src="/AW_LOGO_PKDC-05 1.png"
					alt="Logo"
					class="h-auto w-[200px] max-w-xs md:h-[116px] md:w-[199px]"
				/>
			</div>
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Generative AI:</span></li>
				<li>ชยภัทร อาชีวระงับโรค</li>
				<li>ภูมิปรินทร์ มะโน</li>
				<li>ปิยพร พงษ์ทอง</li>
				<li>พิเชษฐ์ กลั่นชื่น</li>
				<li>พัทธ์ ภัทรานุธาพร</li>
				<li>กรกาญจน์ รุ่งสว่าง</li>
				<li>ธนพล สุขสมรูป</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Artist/Choreographer/Director:</span></li>
				<li>พิเชษฐ์ กลั่นชื่น</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Technology Advisors::</span></li>
				<li>พัทธ์ ภัทรานุธาพร</li>
				<li>ภูมิปรินทร์ มะโน</li>
				<li>ชยภัทร อาชีวระงับโรค</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Dancers:</span></li>
				<li>กรกาญจน์ รุ่งสว่าง</li>
				<li>ธรรศ จงจัดกลาง</li>
				<li>สุนนท์ วชิรรวราการ</li>
				<li>จุฬาลักษณ์ เอกวัฒนพันธ์</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Video Production:</span></li>
				<li>ตรีเทพโปรดักชั่น</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Website & LMS:</span></li>
				<li>ปภัสสิริย์ อภิไพบูลย์</li>
				<li>รินรดา เทพแก้ว</li>
				<li>ไท ปังสกุลยานนท์</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Management & Support Team:</span></li>
				<li>โศจิรัตน์ สิงหลกะ</li>
				<li>กันต์พงศ์ ทวีสุข</li>
				<li>ผดุง จุมพันธ์</li>
			</ul>
		</div>
	{:else}
		<div class="flex flex-col items-center md:w-11/12 md:items-start xl:pl-12">
			<div class="mb-6 flex flex-col items-center md:items-start">
				<img
					src="/AW_LOGO_PKDC-05 1.png"
					alt="Logo"
					class="h-auto w-[200px] max-w-xs md:h-[116px] md:w-[199px]"
				/>
			</div>
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Generative AI:</span></li>
				<li>Chayapatr Archiwaranguprok</li>
				<li>Phoomparin Mano</li>
				<li>Piyaporn Bhongse-tong</li>
				<li>Pichet Klunchun</li>
				<li>Pat Pataranutaporn</li>
				<li>Kornkarn Rungsawang</li>
				<li>Thanapon Suksomroop</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Artist/Choreographer/Director:</span></li>
				<li>Pichet Klunchun</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Technology Advisors::</span></li>
				<li>Pat Pataranutaporn</li>
				<li>Phoomparin Mano</li>
				<li>Chayapatr Archiwaranguprok</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Dancers:</span></li>
				<li>Kornkarn Rungsawang</li>
				<li>Tas Chongchadklang</li>
				<li>Sunon Wachirawarakarn</li>
				<li>Julaluck Eakwattanapun</li>
			</ul>
		</div>

		<div class="flex flex-col items-center space-y-6 p-6 md:w-11/12 md:items-start md:p-0">
			<ul class="text-center md:text-left">
				<li><span class="font-bold">Video Production:</span></li>
				<li>Threethep Production</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Website & LMS:</span></li>
				<li>Papatsiri Apipaiboon</li>
				<li>Rinrada Thepkaew</li>
				<li>Thai Pangsakulyanont</li>
			</ul>

			<ul class="text-center md:text-left">
				<li><span class="font-bold">Management & Support Team:</span></li>
				<li>Sojirat Singholka</li>
				<li>Kanpong Thaweesuk</li>
				<li>Padung Jumpan</li>
			</ul>
		</div>
	{/if}

	<div class="col-span-full mt-12 grid grid-cols-1 gap-12 px-6 pb-12 pt-12 md:grid-cols-2 md:pl-12">
		<div class="flex flex-col items-center text-center md:items-start md:text-left">
			<h2 class="mb-6 text-2xl font-bold text-white md:text-3xl">
				{$_('partners.about_title')}
			</h2>
			<p class="max-w-xl text-base leading-relaxed text-white/90 md:text-lg">
				{$_('partners.about_text')}
			</p>
		</div>

		<div class="flex flex-col items-center">
			<h2 class="mb-8 text-2xl font-bold text-white md:text-3xl">
				{$_('partners.title')}
			</h2>
			<div class="flex flex-wrap items-center justify-center gap-8 md:gap-12">
				<img
					src="/Thai-media-logo.png"
					alt="Thai Media Fund"
					class="h-[120px] w-auto object-contain md:h-[180px]"
				/>
				<img
					src="/tkpark-logo.png"
					alt="TK Park"
					class="h-[120px] w-auto object-contain md:h-[180px]"
				/>
			</div>
		</div>
	</div>
</div>
