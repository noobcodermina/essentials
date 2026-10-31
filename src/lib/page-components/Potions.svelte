<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';
	import ContentCard from '#lib/components/ContentCard.svelte';

	let potionUpgrades = $state([
		{ upgrade: 'Upgrade the Potion', ingredient: 'Glowstone Dust' },
		{ upgrade: 'Extend the Duration', ingredient: 'Redstone Dust' },
		{ upgrade: 'Make it Splash', ingredient: 'Gunpowder' },
		{ upgrade: 'Make it Linger', ingredient: "Dragon's Breath" }
	]);

	let potions = $state([
		{
			name: 'Regeneration',
			steps: [
				{ 0: 'Nether Wart + Water Bottle = Awkward Potion' },
				{ 1: 'Awkward Potion + Ghast Tear = Regeneration I' }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: true,
			isExtendable: false
		},
		{
			name: 'Healing',
			steps: [
				{ 0: 'Nether Wart + Water Bottle = Awkward Potion' },
				{ 1: 'Awkward Potion + Glistering Melon Slice = Healing I' }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: true,
			isExtendable: false
		},
		{
			name: 'Swiftness',
			steps: [
				{ 0: 'Nether Wart + Water Bottle = Awkward Potion' },
				{ 1: 'Awkward Potion + Sugar = Swiftness I' }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: true,
			isExtendable: true
		},
		{
			name: 'Fire Resistance',
			steps: [
				{ 0: 'Nether Wart + Water Bottle = Awkward Potion' },
				{ 1: 'Awkward Potion + Magma Cream = Fire Resistance' }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: false,
			isExtendable: true
		},
		{
			name: 'Night Vision',
			steps: [
				{ 0: 'Nether Wart + Water Bottle = Awkward Potion' },
				{ 1: 'Awkward Potion + Golden Carrot = Night Vision' }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: false,
			isExtendable: true
		},

		{
			name: 'Weakness',
			steps: [{ 0: 'Fermented Spider Eye + Water Bottle = Weakness' }, { 1: '' }],
			isSplash: true,
			isLingering: true,
			isUpgradable: false,
			isExtendable: true
		},
		{
			name: 'Strength',
			steps: [
				{ 0: 'Nether Wart + Water Bottle = Awkward Potion' },
				{ 1: 'Awkward Potion + Blaze Powder = Strength I' }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: true,
			isExtendable: true
		},
		{
			name: 'Slowness',
			steps: [
				{ 0: 'Awkward Potion + Sugar = Swiftness I' },
				{ 1: 'Swiftness I + Fermented Spider Eye = Slowness' }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: false,
			isExtendable: true
		},
		{
			name: 'Leaping',
			steps: [
				{ 0: 'Nether Wart + Water Bottle = Awkward Potion' },
				{ 1: "Awkward Potion + Rabbit's Foot = Leaping I" }
			],
			isSplash: true,
			isLingering: true,
			isUpgradable: true,
			isExtendable: true
		}
	]);
</script>

<TitleDescription title="Potions" description="Every potion recipe" />

{#each potionUpgrades as potionUpgrade (potionUpgrade.upgrade)}
	<ContentCard>
		<p class="content-subtext">{potionUpgrade.upgrade} using: <b>{potionUpgrade.ingredient}</b></p>
	</ContentCard>
{/each}

<div class="potions-wrapper">
	{#each potions as potion (potion.name)}
		<ContentCard>
			<p class="content-name potion-name">{potion.name}</p>

			<p class="content-subtext">{potion.steps[0][0]}</p>
			<p class="content-subtext">{potion.steps[1][1]}</p>

			<p class="content-subtext first-potion-upgrade">
				Extendable duration: <b>{potion.isExtendable}</b>
			</p>
			<p class="content-subtext">Upgradeable: <b>{potion.isUpgradable}</b></p>
			<p class="content-subtext">Make it splash: <b>{potion.isSplash}</b></p>
			<p class="content-subtext">Make it linger: <b>{potion.isLingering}</b></p>
		</ContentCard>
	{/each}
</div>

<style>
	.potions-wrapper {
		margin-top: 2rem;
		.potion-name {
			margin-bottom: 0.5rem;
		}
		.first-potion-upgrade {
			margin-top: 0.5rem;
		}
	}
</style>
