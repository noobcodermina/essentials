<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';
	import ContentCard from '#lib/components/ContentCard.svelte';

	let recipes = $state([
		{
			name: 'Stick',
			ingredients: ['', 'Wood Plank', '', '', 'Wood Plank', '', '', '', ''],
			quantity: 4
		}
	]);
</script>

<TitleDescription title="Recipes" description="Every recipe in the game" />

<div class="recipes-grid">
	{#each recipes as recipe (recipe.name)}
		<ContentCard>
			<p class="content-name recipe-name">{recipe.name} <span>x{recipe.quantity}</span></p>
			<div class="recipe-grid content-subtext">
				{#each recipe.ingredients as ingredient, i (i)}
					<p class="content-subtext">{ingredient}</p>
				{/each}
			</div>
		</ContentCard>
	{/each}
</div>

<style>
	.recipes-grid {
		display: grid;
		grid-template-columns: repeat(3, 1fr);

		.recipe-name {
			span {
				font-size: 0.8rem;
				color: var(--text-light);
			}
		}

		.recipe-grid {
			width: 100%;
			display: grid;
			grid-template-columns: repeat(3, 1fr);
			grid-template-rows: repeat(3, 1fr);
			border: var(--border);

			margin-top: 0.5rem;
			p {
				display: grid;
				place-items: center;

				aspect-ratio: 1;
				border: var(--border);
			}
		}

		:global(.content-wrapper) {
			margin-top: 0 !important;
		}
	}
</style>
