<script>
	import { setContext } from 'svelte';
	let content = $state([
		{ name: 'kralj', content: '1' },
		{ name: 'jason', content: '2' },
		{ name: 'stake', content: '3' }
	]);

	let splitedContent = $state([]);

	let searchQuery = $state('');
	setContext('searchQuery', () => searchQuery);

	for (let i = 0; i < content.length; i++) {
		splitedContent.push(content[i].name.split(''));
		console.log(splitedContent);

		if (searchQuery.includes(splitedContent[0])) {
			console.log('ima');
		}
	}
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
