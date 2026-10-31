<script>
	let content = $state([
		{ name: '111', content: '1' },
		{ name: '2', content: '2' },
		{ name: '3', content: '3' }
	]);

	let searchQuery = $state('');

	$effect(() => {
		console.log(searchQuery.includes(content[0].name));
	});
</script>

<input type="text" bind:value={searchQuery} />

<p>{searchQuery}</p>

{#each content as c (c.name)}
	<div>
		<p>{c.name}</p>
		<p>{c.content}</p>
	</div>
{/each}

<style>
	div {
		background-color: gray;
		margin-top: 20px;
	}
</style>
