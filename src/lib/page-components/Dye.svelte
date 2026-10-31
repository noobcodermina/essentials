<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';
	import ContentCard from '#lib/components/ContentCard.svelte';
	let dye = $state([
		{ name: 'White', ingredients: 'Bone Meal, Lily of the Valley', hex: 'F9FFFE' },
		{
			name: 'Light Gray',
			ingredients:
				'Black Dye + White Dye + White Dye, Gray Dye + White Dye, Azure Bluet, Oxeye Daisy, White Tulip',
			hex: '9D9D97'
		},
		{ name: 'Gray', ingredients: 'Black Dye + White Dye, Closed Eyeblossom', hex: '474F52' },
		{ name: 'Black', ingredients: 'Ink Sac, Wither Rose', hex: '1D1D21' },
		{ name: 'Brown', ingredients: 'Cocoa Beans', hex: '835432' },
		{ name: 'Red', ingredients: 'Poppy, Red Tulip, Rose Bush, Beetroot', hex: 'B02E26' },
		{
			name: 'Orange',
			ingredients: 'Yellow Dye + Red Dye, Orange Tulip, Torchflower, Open Eyeblossom',
			hex: 'F9801D'
		},
		{
			name: 'Yellow',
			ingredients: 'Dandelion, Sunflower, Wildflowers',
			hex: 'FED83D'
		},

		{
			name: 'Green',
			ingredients: 'Smelted Cactus',
			hex: '5E7C16'
		},
		{
			name: 'Lime',
			ingredients: 'Green Dye + White Dye, Smelted Sea Pickle',
			hex: '80C71F'
		},
		{
			name: 'Cyan',
			ingredients: 'Green Dye + Blue Dye, Pitcher Plant',
			hex: '169C9C'
		},
		{
			name: 'Light Blue',
			ingredients: 'White Dye + Blue Dye, Blue Orchid',
			hex: '3AB3DA'
		},
		{
			name: 'Blue',
			ingredients: 'Lapis Lazuli, Cornflower',
			hex: '3C44AA'
		},
		{
			name: 'Purple',
			ingredients: 'Red Dye + Blue Dye',
			hex: '8932B8'
		},
		{
			name: 'Magenta',
			ingredients:
				'Purple Dye + Pink Dye, Red Dye + Red Dye + Blue Dye + White Dye, Pink Dye + Red Dye + Blue Dye, Allium, Lilac',
			hex: 'C74EBD'
		},
		{
			name: 'Pink',
			ingredients: 'Red Dye + White Dye, Pink Tulip, Peony, Pink Petals, Cactus Flower',
			hex: 'F38BAA'
		}
	]);
</script>

<TitleDescription title="Dye" description="Learn how to make every type of dye" />

{#each dye as d (d.name)}
	<ContentCard>
		<span class="color-showcase" style="background-color: #{d.hex};"></span>
		<p class="content-name">{d.name}</p>
		<p class="content-subtext">{d.ingredients}</p>
	</ContentCard>
{/each}

<style>
	.color-showcase {
		display: block;
		width: 1rem;
		height: 1rem;
		border: 1px solid var(--highlight);
	}
</style>
