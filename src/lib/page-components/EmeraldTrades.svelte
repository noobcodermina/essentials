<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';
	import ContentCard from '#lib/components/ContentCard.svelte';

	let emeraldTrades = $state([
		// Farmer
		{
			name: 'Wheat',
			requiredQuantity: 20,
			howToTrade: 'Turn a villager into a farmer using composter',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Potato',
			requiredQuantity: 26,
			howToTrade: 'Turn a villager into a farmer using composter',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Carrot',
			requiredQuantity: 22,
			howToTrade: 'Turn a villager into a farmer using composter',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Beetroot',
			requiredQuantity: 15,
			howToTrade: 'Turn a villager into a farmer using composter',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Pumpkin',
			requiredQuantity: 6,
			howToTrade: 'Turn a villager into a farmer using composter',
			requiredLevel: '2 [Apprentice]'
		},
		{
			name: 'Melon',
			requiredQuantity: 4,
			howToTrade: 'Turn a villager into a farmer using composter',
			requiredLevel: '3 [Journeyman]'
		},
		// Fisherman
		{
			name: 'Coal',
			requiredQuantity: 10,
			howToTrade: 'Turn a villager into a fisherman using barrel',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Raw Cod',
			requiredQuantity: 15,
			howToTrade: 'Turn a villager into a fisherman using barrel',
			requiredLevel: '2 [Apprentice]'
		},
		{
			name: 'Raw Salmon',
			requiredQuantity: 13,
			howToTrade: 'Turn a villager into a fisherman using barrel',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Tropical Fish',
			requiredQuantity: 6,
			howToTrade: 'Turn a villager into a fisherman using barrel',
			requiredLevel: '4 [Expert]'
		},
		{
			name: 'Pufferfish',
			requiredQuantity: 4,
			howToTrade: 'Turn a villager into a fisherman using barrel',
			requiredLevel: '5 [Master]'
		},
		{
			name: 'Boat',
			requiredQuantity: 1,
			howToTrade: 'Turn a villager into a fisherman using barrel',
			requiredLevel: '5 [Master]'
		},
		// Fletcher
		{
			name: 'Stick',
			requiredQuantity: 32,
			howToTrade: 'Turn a villager into a fletcher using fletching table',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Flint',
			requiredQuantity: 26,
			howToTrade: 'Turn a villager into a fletcher using fletching table',
			requiredLevel: '2 [Apprentice]'
		},
		{
			name: 'String',
			requiredQuantity: 14,
			howToTrade: 'Turn a villager into a fletcher using fletching table',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Feather',
			requiredQuantity: 24,
			howToTrade: 'Turn a villager into a fletcher using fletching table',
			requiredLevel: '4 [Expert]'
		},
		{
			name: 'Tripwire Hook',
			requiredQuantity: 8,
			howToTrade: 'Turn a villager into a fletcher using fletching table',
			requiredLevel: '5 [Master]'
		},
		// Leatherworker
		{
			name: 'Leather',
			requiredQuantity: 6,
			howToTrade: 'Turn a villager into a leatherworker using cauldron',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Rabbit Hide',
			requiredQuantity: 9,
			howToTrade: 'Turn a villager into a leatherworker using cauldron',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Turtle Scute',
			requiredQuantity: 4,
			howToTrade: 'Turn a villager into a leatherworker using cauldron',
			requiredLevel: '4 [Expert]'
		},
		// Librarian
		{
			name: 'Paper',
			requiredQuantity: 24,
			howToTrade: 'Turn a villager into a librarian using lectern',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Book',
			requiredQuantity: 4,
			howToTrade: 'Turn a villager into a librarian using lectern',
			requiredLevel: '2 [Apprentice]'
		},
		{
			name: 'Ink Sac',
			requiredQuantity: 5,
			howToTrade: 'Turn a villager into a librarian using lectern',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Book and Quill',
			requiredQuantity: 1,
			howToTrade: 'Turn a villager into a librarian using lectern',
			requiredLevel: '4 [Expert]'
		},
		// Cartographer
		{
			name: 'Glass Pane',
			requiredQuantity: 11,
			howToTrade: 'Turn a villager into a cartographer using cartography table',
			requiredLevel: '2 [Apprentice]'
		},
		{
			name: 'Compass',
			requiredQuantity: 1,
			howToTrade: 'Turn a villager into a cartographer using cartography table',
			requiredLevel: '3 [Journeyman]'
		},
		// Cleric
		{
			name: 'Rotten Flesh',
			requiredQuantity: 32,
			howToTrade: 'Turn a villager into a cleric using brewing stand',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Gold Ingot',
			requiredQuantity: 3,
			howToTrade: 'Turn a villager into a cleric using brewing stand',
			requiredLevel: '2 [Apprentice]'
		},
		{
			name: "Rabbit's Foot",
			requiredQuantity: 2,
			howToTrade: 'Turn a villager into a cleric using brewing stand',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Glass Bottle',
			requiredQuantity: 9,
			howToTrade: 'Turn a villager into a cleric using brewing stand',
			requiredLevel: '4 [Expert]'
		},
		{
			name: 'Nether Wart',
			requiredQuantity: 22,
			howToTrade: 'Turn a villager into a cleric using brewing stand',
			requiredLevel: '5 [Master]'
		},
		// Toolsmith
		{
			name: 'Iron Ingot',
			requiredQuantity: 4,
			howToTrade: 'Turn a villager into a toolsmith using smithing table',
			requiredLevel: '2 [Apprentice]'
		},
		// Armorer
		{
			name: 'Lava Bucket',
			requiredQuantity: 1,
			howToTrade: 'Turn a villager into an armorer using blast furnace',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Diamond',
			requiredQuantity: 1,
			howToTrade: 'Turn a villager into an armorer using blast furnace',
			requiredLevel: '3 [Journeyman]'
		},
		// Shepherd
		{
			name: 'Wool',
			requiredQuantity: 18,
			howToTrade: 'Turn a villager into a shepherd using loom',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Dye',
			requiredQuantity: 12,
			howToTrade: 'Turn a villager into a shepherd using loom',
			requiredLevel: '2 [Apprentice]'
		},
		// Butcher
		{
			name: 'Raw Porkchop',
			requiredQuantity: 7,
			howToTrade: 'Turn a villager into a butcher using smoker',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Raw Chicken',
			requiredQuantity: 14,
			howToTrade: 'Turn a villager into a butcher using smoker',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Raw Rabbit',
			requiredQuantity: 4,
			howToTrade: 'Turn a villager into a butcher using smoker',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Raw Mutton',
			requiredQuantity: 7,
			howToTrade: 'Turn a villager into a butcher using smoker',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Raw Beef',
			requiredQuantity: 10,
			howToTrade: 'Turn a villager into a butcher using smoker',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Dried Kelp Block',
			requiredQuantity: 10,
			howToTrade: 'Turn a villager into a butcher using smoker',
			requiredLevel: '4 [Expert]'
		},
		{
			name: 'Sweet Berries',
			requiredQuantity: 10,
			howToTrade: 'Turn a villager into a butcher using smoker',
			requiredLevel: '5 [Master]'
		},
		// Mason
		{
			name: 'Clay Ball',
			requiredQuantity: 10,
			howToTrade: 'Turn a villager into a mason using stonecutter',
			requiredLevel: '1 [Novice]'
		},
		{
			name: 'Stone',
			requiredQuantity: 20,
			howToTrade: 'Turn a villager into a mason using stonecutter',
			requiredLevel: '2 [Apprentice]'
		},
		{
			name: 'Granite',
			requiredQuantity: 16,
			howToTrade: 'Turn a villager into a mason using stonecutter',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Andesite',
			requiredQuantity: 16,
			howToTrade: 'Turn a villager into a mason using stonecutter',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Diorite',
			requiredQuantity: 16,
			howToTrade: 'Turn a villager into a mason using stonecutter',
			requiredLevel: '3 [Journeyman]'
		},
		{
			name: 'Nether Quartz',
			requiredQuantity: 12,
			howToTrade: 'Turn a villager into a mason using stonecutter',
			requiredLevel: '4 [Expert]'
		}
	]);
</script>

<TitleDescription title="Emerald Trades" description="Every trade that can give you emeralds" />

{#each emeraldTrades as emeraldTrade (emeraldTrade.name)}
	<ContentCard>
		<p class="content-name trade-name">{emeraldTrade.name}</p>
		<p class="content-subtext">{emeraldTrade.howToTrade}</p>
		<p class="content-subtext">Required Level: {emeraldTrade.requiredLevel}</p>
		<p class="trade">
			Trade {emeraldTrade.requiredQuantity}
			{emeraldTrade.name} for 1 Emerald
		</p>
	</ContentCard>
{/each}

<style>
	.trade-name {
		margin-bottom: 0.5rem;
	}
	.trade {
		margin-top: 0.5rem;
	}
</style>
