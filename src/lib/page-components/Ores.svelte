<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';
	import ContentCard from '#lib/components/ContentCard.svelte';

	let ores = $state([
		{
			name: 'Coal',
			Y: 96,
			minTool: 'Wooden',
			fortuneDrops: [{ 0: '1' }, { 1: '1-2' }, { 2: '1-3' }, { 3: '1-4' }]
		},
		{
			name: 'Copper',
			Y: 48,
			minTool: 'Stone',
			fortuneDrops: [{ 0: '2-5' }, { 1: '2-10' }, { 2: '2-15' }, { 3: '2-20' }]
		},
		{
			name: 'Iron',
			Y: '16 / 232',
			minTool: 'Stone',
			fortuneDrops: [{ 0: '1' }, { 1: '1-2' }, { 2: '1-3' }, { 3: '1-4' }]
		},
		{
			name: 'Gold',
			Y: -16,
			minTool: 'Iron',
			fortuneDrops: [{ 0: '1' }, { 1: '1-2' }, { 2: '1-3' }, { 3: '1-4' }]
		},
		{
			name: 'Amethyst',
			Y: '-40 to -48',
			minTool: 'Any',
			fortuneDrops: [{ 0: '4' }, { 1: '4 or 8' }, { 2: '4, 8 or 12' }, { 3: '4, 8, 12 or 16' }]
		},
		{
			name: 'Lapis',
			Y: '0',
			minTool: 'Stone',
			fortuneDrops: [{ 0: '4-9' }, { 1: '8-18' }, { 2: '8-27' }, { 3: '8-36' }]
		},
		{
			name: 'Redstone',
			Y: '-59',
			minTool: 'Iron',
			fortuneDrops: [{ 0: '4-5' }, { 1: '4-6' }, { 2: '4-7' }, { 3: '4-8' }]
		},
		{
			name: 'Diamond',
			Y: '-59',
			minTool: 'Iron',
			fortuneDrops: [{ 0: '1' }, { 1: '1-2' }, { 2: '1-3' }, { 3: '1-4' }]
		},
		{
			name: 'Emerald',
			Y: '232',
			minTool: 'Iron',
			fortuneDrops: [{ 0: '1' }, { 1: '1-2' }, { 2: '1-3' }, { 3: '1-4' }]
		},
		{
			name: 'Quartz',
			Y: 'Any',
			minTool: 'Any',
			fortuneDrops: [{ 0: '1' }, { 1: '1-2' }, { 2: '1-3' }, { 3: '1-4' }]
		},
		{
			name: 'Nether Gold',
			Y: 'Any',
			minTool: 'Any',
			fortuneDrops: [{ 0: '2-6' }, { 1: '4-12' }, { 2: '4-18' }, { 3: '4-24' }]
		},
		{
			name: 'Ancient Debris',
			Y: '15 / 16',
			minTool: 'Diamond',
			fortuneDrops: [{ 0: '1' }, { 1: '1' }, { 2: '1' }, { 3: '1' }]
		}
	]);
</script>

<TitleDescription title="Ores" description="Learn usefull stuff about ores" />

<div class="ores-grid">
	{#each ores as ore (ore.name)}
		<ContentCard>
			<p class="content-name">{ore.name}</p>
			<p class="content-subtext">Best Y Level: {ore.Y}</p>
			<p class="content-subtext">Minimal Tool: {ore.minTool} Pickaxe</p>

			<i>//drops based on fortune level</i>

			<p class="content-subtext">No Fortune: {ore.fortuneDrops[0][0]}</p>
			<p class="content-subtext">Fortune I: {ore.fortuneDrops[1][1]}</p>
			<p class="content-subtext">Fortune II: {ore.fortuneDrops[2][2]}</p>
			<p class="content-subtext">Fortune III: {ore.fortuneDrops[3][3]}</p>
		</ContentCard>
	{/each}
</div>

<style>
	.ores-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		:global(.content-wrapper) {
			margin-top: 0 !important;
		}
		i {
			padding: 1rem 0;
		}
	}
</style>
