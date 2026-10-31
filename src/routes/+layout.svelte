<script lang="ts">
	import '../app.css';
	import type { LayoutProps } from './$types';

	import Header from '#lib/components/Header.svelte';
	import Button from '#lib/components/Button.svelte';

	import Advancements from '#lib/page-components/Advancements.svelte';
	import Coordinates from '#lib/page-components/Coordinates.svelte';
	import Dye from '#lib/page-components/Dye.svelte';
	import EmeraldTrades from '#lib/page-components/EmeraldTrades.svelte';
	import Enchanting from '#lib/page-components/Enchanting.svelte';
	import FarmsList from '#lib/page-components/FarmsList.svelte';
	import GoatHorns from '#lib/page-components/GoatHorns.svelte';
	import Hotkeys from '#lib/page-components/Hotkeys.svelte';
	import ItemsTracker from '#lib/page-components/ItemsTracker.svelte';
	import MusicDiscs from '#lib/page-components/MusicDiscs.svelte';
	import Ores from '#lib/page-components/Ores.svelte';
	import Potions from '#lib/page-components/Potions.svelte';
	import Recipes from '#lib/page-components/Recipes.svelte';
	import Trims from '#lib/page-components/Trims.svelte';
	import Test from '#lib/page-components/Test.svelte';
	let sections = $state([
		{ name: 'Advancements', component: Advancements },
		{ name: 'Recipes', component: Recipes },
		{ name: 'Trims', component: Trims },
		{ name: 'Dye', component: Dye },
		{ name: 'Emerald Trades', component: EmeraldTrades },
		{ name: 'Ores', component: Ores },
		{ name: 'Potions', component: Potions },
		{ name: 'Coordinates', component: Coordinates },
		{ name: 'Farms List', component: FarmsList },
		{ name: 'Goat Horns', component: GoatHorns },
		{ name: 'Music Discs', component: MusicDiscs },
		{ name: 'Items Tracker', component: ItemsTracker },
		{ name: 'Hotkeys', component: Hotkeys },
		{ name: 'Enchanting', component: Enchanting },
		{ name: 'Test', component: Test }
	]);

	let SelectedSection = $state(sections[0].component);

	let { children }: LayoutProps = $props();
</script>

<div class="layout-wrapper">
	<Header />

	<div class="sorter-wrapper">
		{#each sections as section (section.name)}
			<Button
				selected={SelectedSection == section.component}
				onclick={() => {
					SelectedSection = section.component;
				}}>{section.name}</Button
			>
		{/each}
	</div>

	<SelectedSection />
	{@render children()}
</div>

<style>
	.layout-wrapper {
		width: min(100%, 1000px);
		padding-bottom: 2rem;
		margin: auto;
	}
</style>
