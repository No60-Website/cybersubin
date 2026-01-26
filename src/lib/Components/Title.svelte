<script>
	export let head = '';
	export let title = '';
	export let color = 'text-white';
	export let h4Style = '';
	export let h4Class = '';
</script>

<div>
	<h2 class={`text-2xl font-bold md:text-3xl ${color}`}>{head}</h2>
	<h4 style={h4Style} class={`text-4xl text-white md:text-6xl xl:w-min ${h4Class}`}>{title}</h4>
</div>
