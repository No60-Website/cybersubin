<script>
	export let text = '';
	export let highlightColor = '#C5A46D';

	// Parse text with *word* markers and split into parts
	function parseText(input) {
		const parts = [];
		const regex = /\*([^*]+)\*/g;
		let lastIndex = 0;
		let match;

		while ((match = regex.exec(input)) !== null) {
			// Add text before the match
			if (match.index > lastIndex) {
				parts.push({
					type: 'text',
					content: input.substring(lastIndex, match.index)
				});
			}

			// Add highlighted word
			parts.push({
				type: 'highlight',
				content: match[1]
			});

			lastIndex = match.index + match[0].length;
		}

		// Add remaining text
		if (lastIndex < input.length) {
			parts.push({
				type: 'text',
				content: input.substring(lastIndex)
			});
		}

		return parts.length ? parts : [{ type: 'text', content: input }];
	}

	$: parts = parseText(text);
</script>

{#each parts as part (part.content)}
	{#if part.type === 'highlight'}
		<span style="color: {highlightColor};">{part.content}</span>
	{:else}
		{part.content}
	{/if}
{/each}
