<script>
	import { openPastDialog } from '$lib/store';
	import { _ } from 'svelte-i18n';
	import Title_wild from '$lib/Components/Title_wild.svelte';
	import TitleWild from '$lib/Components/Title_wild.svelte';
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div
	class="fixed left-0 top-0 z-[120] flex h-[100dvh] w-screen items-center justify-center bg-black/90 p-4 md:p-8"
	on:click={() => {
		$openPastDialog = false;
	}}
>
	<div
		class="relative flex max-h-full w-[900px] flex-col overflow-hidden rounded-lg bg-neutral-900 md:flex-row"
		on:click|stopPropagation
	>
		<!-- Left Sidebar -->
		<div class="flex flex-col border-b border-neutral-800 p-6 md:w-64 md:border-b-0 md:border-r">
			<div>
				<p class="mb-2 text-sm font-bold tracking-wider text-gold">{$_('menu.past')}</p>
				<h2
					class="mb-6 text-4xl font-normal leading-tight text-white md:text-5xl"
					style="font-family: 'Archivo', 'noto sans thai', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, 'Noto Sans', 'Liberation Sans', sans-serif;"
				>
					<TitleWild
						title={$_('past.popup1') + '\n' + $_('past.popup2') + '\n' + $_('past.popup3')}/>
					
				</h2>
				<p class="text-sm leading-relaxed text-neutral-400">
					{$_('past.hero2.tagline')}
				</p>
			</div>

			<!-- Vertical caption at bottom of sidebar -->
			<div class="mt-8 hidden md:block">
				<div class="border-l-2 border-gold pl-4">
					<p class="text-xs leading-relaxed text-gold">
						{$_('past.hero2.caption')}
					</p>
				</div>
			</div>
		</div>

		<!-- Right Content Area -->
		<div class="flex-1 overflow-y-auto">
			<!-- Image at top -->
			<div class="w-full overflow-hidden bg-neutral-800">
				<img src="/intro/present.png" class="h-48 w-full object-cover md:h-64" alt="Mae Bot Yai" />
			</div>

			<!-- Two columns of text -->
			<div class="grid gap-6 p-6 text-sm leading-relaxed text-neutral-300 md:grid-cols-2 md:p-8">
				<div>
					<p>{$_('past.hero2.p1')}</p>
				</div>
				<div>
					<p>{$_('past.hero2.p2')}</p>
				</div>
			</div>
		</div>

		<!-- Close button -->
		<button
			class="absolute right-4 top-4 text-2xl text-white transition-colors hover:text-gold"
			on:click={() => {
				$openPastDialog = false;
			}}
			aria-label="Close"
		>
			×
		</button>
	</div>
</div>

<style>
	/* Custom scrollbar for the content area */
	::-webkit-scrollbar {
		width: 8px;
	}
	::-webkit-scrollbar-track {
		background: #171717;
	}
	::-webkit-scrollbar-thumb {
		background: #404040;
		border-radius: 4px;
	}
	::-webkit-scrollbar-thumb:hover {
		background: #525252;
	}
</style>
