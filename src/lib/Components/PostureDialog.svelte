<script>
	import Figure from './Figure.svelte';
	import { openDialog, current, slider } from '$lib/store';
	import { posture } from '$lib/59';
	import { locale } from 'svelte-i18n';

	let img = true;
	let opacity = 0;
	let playing = false;
	let pressedKey = null;

	$: if ($current) { playing = false; img = true; opacity = 0; }

	function navigate(direction) {
		if (direction === 'next') {
			$current = $current === 59 ? 1 : $current + 1;
		} else {
			$current = $current === 1 ? 59 : $current - 1;
		}
	}

	function handleKeydown(e) {
		if (pressedKey === e.key) return; // Already handling this key

		if (e.key === 'ArrowRight') {
			e.preventDefault();
			pressedKey = e.key;
			navigate('next');
		} else if (e.key === 'ArrowLeft') {
			e.preventDefault();
			pressedKey = e.key;
			navigate('prev');
		}
	}

	function handleKeyup(e) {
		if (e.key === 'ArrowLeft' || e.key === 'ArrowRight') {
			pressedKey = null;
		}
	}
</script>

<svelte:window on:keydown={handleKeydown} on:keyup={handleKeyup} />

<!-- svelte-ignore a11y-no-static-element-interactions -->
<!-- svelte-ignore a11y-click-events-have-key-events -->
<div
	class="fixed left-0 top-0 z-[120] flex h-[100dvh] w-screen items-center justify-center bg-black/80 md:p-4"
>
	<div
		class="glass relative grid max-h-full w-full min-w-[50%] max-w-4xl gap-4 rounded-md border border-neutral-800 bg-neutral-900 p-4 text-white shadow-md lg:h-auto lg:flex-row"
	>
		<!-- Left Arrow Button -->
		<button
			class="absolute left-4 top-1/2 z-50 flex h-10 w-10 -translate-y-1/2 items-center justify-center text-white opacity-60 transition hover:opacity-100 focus:outline-none"
			on:click={() => navigate('prev')}
			aria-label="Previous movement"
			tabindex="-1"
		>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6"
				viewBox="0 0 24 24"
				fill="none"
				stroke="currentColor"
				stroke-width="2"
			>
				<polyline points="15 18 9 12 15 6"></polyline>
			</svg>
		</button>

		<!-- Right Arrow Button -->
		<button
			class="absolute right-4 top-1/2 z-50 flex h-10 w-10 -translate-y-1/2 items-center justify-center text-white opacity-60 transition hover:opacity-100 focus:outline-none"
			on:click={() => navigate('next')}
			aria-label="Next movement"
			tabindex="-1"
		>
			<svg
				xmlns="http://www.w3.org/2000/svg"
				class="h-6 w-6"
				viewBox="0 0 24 24"
				fill="none"
				stroke="currentColor"
				stroke-width="2"
			>
				<polyline points="9 18 15 12 9 6"></polyline>
			</svg>
		</button>

		<h3 class="w-full text-wrap pr-10 text-xl text-center">
			{#if $locale === 'th'}
				<span class="font-bold text-gold">แม่บทที่ {$current}</span><br />
				{posture[$current - 1].thai}
				({posture[$current - 1].english})
			{:else}
				<span class="font-bold text-gold">Pose {$current}</span><br />
				{posture[$current - 1].english}
				({posture[$current - 1].thai})
			{/if}
		</h3>
		<div class="w-full gap-2 overflow-hidden md:flex md:flex-row">
			<div
				class="relative hidden aspect-[3/4] w-full overflow-hidden rounded-md border border-neutral-700 bg-black md:block"
			>
				<img src={`/original/${$current}.jpg`} class="min-h-full min-w-full object-cover" alt="" />
				<div class="absolute left-0 top-0 h-full w-full" style={`opacity: ${opacity}%`}>
					<img src={`/diagram/${$current}.png`} class="min-h-full min-w-full object-cover" alt="" />
				</div>
				<div class="absolute bottom-0 left-0 z-50 mb-2 h-8 w-full px-4">
					<input
						type="range"
						name=""
						bind:value={opacity}
						class="mb-6 h-1 w-full cursor-pointer appearance-none rounded-lg bg-neutral-500 accent-neutral-200"
						id=""
					/>
				</div>
			</div>
			<div
				class="relative aspect-[3/4] max-h-full w-full overflow-hidden rounded-md border border-neutral-700 bg-black hover:cursor-grab"
			>
				{#key $current}
					<Figure i={+$current} seek={$slider} {playing} />
					{#if !playing}
						<button
							class="absolute left-1/2 top-1/2 z-50 h-16 w-16 -translate-x-1/2 -translate-y-1/2 items-center justify-center rounded-full bg-white/20 text-white backdrop-blur-sm transition hover:bg-white/30 {img ? 'hidden md:flex' : 'flex'}"
							on:click={() => (playing = true)}
						>
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="h-8 w-8"
								viewBox="0 0 24 24"
								fill="currentColor"
							>
								<path d="M8 5v14l11-7z" />
							</svg>
						</button>
					{/if}
					<button
						class="hover:text-red-500 absolute bottom-[10px] left-4 z-50 items-center justify-center text-white transition {img ? 'hidden md:flex' : 'flex'}"
						on:click={() => (playing = !playing)}
					>
						{#if playing}
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="h-7 w-7"
								viewBox="0 0 24 24"
								fill="currentColor"
							>
								<path d="M6 19h4V5H6v14zm8-14v14h4V5h-4z" />
							</svg>
						{:else}
							<svg
								xmlns="http://www.w3.org/2000/svg"
								class="h-7 w-7"
								viewBox="0 0 24 24"
								fill="currentColor"
							>
								<path d="M8 5v14l11-7z" />
							</svg>
						{/if}
					</button>
					<div class="absolute bottom-0 left-9 right-0 z-50 mb-2 h-8 px-4 {img ? 'hidden md:block' : ''}">
						<input
							type="range"
							name=""
							bind:value={$slider}
							class="mb-6 h-1 w-full cursor-pointer appearance-none rounded-lg bg-neutral-500 accent-neutral-200"
							id=""
						/>
					</div>
				{/key}
				{#if img}
					<div class="absolute right-0 top-0 aspect-[3/4] h-full w-full md:hidden">
						<img
							src={`/original/${$current}.jpg`}
							class="min-h-full min-w-full object-cover"
							alt=""
						/>
						<div class="absolute left-0 top-0 h-full w-full" style={`opacity: ${opacity}%`}>
							<img
								src={`/diagram/${$current}.png`}
								class="min-h-full min-w-full object-cover"
								alt=""
							/>
						</div>
						<div class="absolute bottom-0 left-0 z-50 mb-2 h-8 w-full px-4">
							<input
								type="range"
								name=""
								bind:value={opacity}
								class="mb-6 h-1 w-full cursor-pointer appearance-none rounded-lg bg-neutral-500 accent-neutral-200"
								id=""
							/>
						</div>
					</div>
				{/if}
			</div>

			<div class="mt-3 flex items-center justify-center gap-2 md:hidden">
				<div>3D</div>
				<div
					class={`flex aspect-[3/2] h-8 rounded-full border p-1 ${img ? 'justify-end' : ''}`}
					on:click={() => {
						img = !img;
					}}
				>
					<div class="flex aspect-square h-full rounded-full bg-white"></div>
				</div>
				<div>Image</div>
			</div>
		</div>
		<div
			class="absolute right-0 top-0 m-2 cursor-pointer text-white hover:font-bold"
			on:click={() => {
				$openDialog = false;
			}}
		>
			[x]
		</div>
	</div>
</div>
