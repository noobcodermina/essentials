<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';

	import ContentCard from '#lib/components/ContentCard.svelte';

	let trims = $state([
		{
			name: 'Sentry',
			foundIn: 'Pillager Outpost Chests',
			dropChance: '~20-25%',
			duplicationRecipe: [
				'Diamond',
				'Sentry Template',
				'Diamond',
				'Diamond',
				'Cobblestone',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Vex',
			foundIn: 'Woodland Mansion Chests',
			dropChance: '~50%',
			duplicationRecipe: [
				'Diamond',
				'Vex Template',
				'Diamond',
				'Diamond',
				'Cobblestone',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Wild',
			foundIn: 'Jungle Temple Chests',
			dropChance: '~20%',
			duplicationRecipe: [
				'Diamond',
				'Wild Template',
				'Diamond',
				'Diamond',
				'Mossy Cobblestone',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Coast',
			foundIn: 'Shipwreck Chests',
			dropChance: '~16.7%',
			duplicationRecipe: [
				'Diamond',
				'Coast Template',
				'Diamond',
				'Diamond',
				'Cobblestone',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Dune',
			foundIn: 'Desert Temple Chests',
			dropChance: '~14.3%',
			duplicationRecipe: [
				'Diamond',
				'Dune Template',
				'Diamond',
				'Diamond',
				'Sandstone',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Wayfinder',
			foundIn: 'Trail Ruins Sus. Gravel',
			dropChance: '~8.3%',
			duplicationRecipe: [
				'Diamond',
				'Wayfinder Template',
				'Diamond',
				'Diamond',
				'Terracota',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Raiser',
			foundIn: 'Trail Ruins Sus. Gravel',
			dropChance: '8.3%',
			duplicationRecipe: [
				'Diamond',
				'Raiser Template',
				'Diamond',
				'Diamond',
				'Terracota',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},

		{
			name: 'Shaper',
			foundIn: 'Trail Ruins Sus. Gravel',
			dropChance: '8.3%',
			duplicationRecipe: [
				'Diamond',
				'Shaper Template',
				'Diamond',
				'Diamond',
				'Terracota',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Host',
			foundIn: 'Trail Ruins Sus. Gravel',
			dropChance: '8.3%',
			duplicationRecipe: [
				'Diamond',
				'Host Template',
				'Diamond',
				'Diamond',
				'Terracota',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Ward',
			foundIn: 'Ancient City Chests',
			dropChance: '~5%',
			duplicationRecipe: [
				'Diamond',
				'Ward Template',
				'Diamond',
				'Diamond',
				'Cobbled Deepslate',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Silence',
			foundIn: 'Ancient City Chests',
			dropChance: '~14.3%',
			duplicationRecipe: [
				'Diamond',
				'Silence Template',
				'Diamond',
				'Diamond',
				'Cobbled Deepslate',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Tide',
			foundIn: 'Elder Guardian Drop',
			dropChance: '~20%',
			duplicationRecipe: [
				'Diamond',
				'Tide Template',
				'Diamond',
				'Diamond',
				'Prismarine',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Snout',
			foundIn: 'Bastion Remnaint Chests',
			dropChance: '~8.3%',
			duplicationRecipe: [
				'Diamond',
				'Snout Template',
				'Diamond',
				'Diamond',
				'Blackstone',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Rib',
			foundIn: 'Nether Fortress Chests',
			dropChance: '~6.7%',
			duplicationRecipe: [
				'Diamond',
				'Rib Template',
				'Diamond',
				'Diamond',
				'Netherrack',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Eye',
			foundIn: 'Stronghold Library Chests',
			dropChance: '100%',
			duplicationRecipe: [
				'Diamond',
				'Eye Template',
				'Diamond',
				'Diamond',
				'Endstone',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Spire',
			foundIn: 'End City Chests',
			dropChance: '~6.7%',
			duplicationRecipe: [
				'Diamond',
				'Spire Template',
				'Diamond',
				'Diamond',
				'Purpur Block',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Flow',
			foundIn: 'Ominous Vaults [Trial Chambers]',
			dropChance: '~22.5%',
			duplicationRecipe: [
				'Diamond',
				'Flow Template',
				'Diamond',
				'Diamond',
				'Breeze Rod',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		},
		{
			name: 'Bolt',
			foundIn: 'Standard Vaults [Trial Chambers]',
			dropChance: '~5.4%',
			duplicationRecipe: [
				'Diamond',
				'Bolt Template',
				'Diamond',
				'Diamond',
				'Block of Copper',
				'Diamond',
				'Diamond',
				'Diamond',
				'Diamond'
			]
		}
	]);
</script>

<TitleDescription title="Trims" description="Armor trim guide + tracker" />

<div class="trims-grid">
	{#each trims as trim (trim.name)}
		<ContentCard>
			<p class="content-name trim-name">{trim.name}</p>
			<p class="content-subtext">Found in: {trim.foundIn}</p>
			<p class="content-subtext">Drop Chance: {trim.dropChance}</p>

			<i>Duplication Recipe:</i>
			<div class="trim-grid">
				{#each trim.duplicationRecipe as duplicationRecipe, i (i)}
					<p class="content-subtext">{duplicationRecipe}</p>
				{/each}
			</div>
		</ContentCard>
	{/each}
</div>

<style>
	.trims-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		.trim-name {
			margin-bottom: 0.5rem;
		}
		i {
			margin-top: 0.5rem;
		}
		.trim-grid {
			display: grid;
			grid-template-rows: repeat(3, 1fr);
			grid-template-columns: repeat(3, 1fr);
			width: 100%;
			aspect-ratio: 1;
			border: var(--border);
			margin-top: 0.25rem;

			p {
				border: var(--border);
				display: grid;
				place-items: center;
				text-align: center;
			}
		}
		:global(.content-wrapper) {
			margin-top: 0 !important;
		}
	}
</style>
