<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';

	import ContentCard from '#lib/components/ContentCard.svelte';

	let discs = $state([
		{
			name: '13',
			howToObtain:
				'Skeleton, Stray, Bogged or Parched kills a Creeper, Chest loot: [Dungeons, Woodland Mansions, Ancient Cities]'
		},
		{
			name: 'Cat',
			howToObtain:
				'Skeleton, Stray, Bogged or Parched kills a Creeper, Chest loot: [Dungeons, Woodland Mansions, Ancient Cities]'
		},
		{
			name: 'Blocks',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Chirp',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Far',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Mall',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Mellohi',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Stal',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Strad',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Ward',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: '11',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Wait',
			howToObtain: 'Skeleton, Stray, Bogged or Parched kills a Creeper'
		},
		{
			name: 'Pigstep',
			howToObtain: 'Bastion Remnants Chest Loot'
		},
		{
			name: 'Otherside',
			howToObtain: 'Chest loot from Dungeons, Strongholds, Ancient Cities'
		},
		{
			name: 'Creator',
			howToObtain: 'Drops From Ominous Vaults inside Trial Chambers.'
		},
		{
			name: 'Creator (music box)',
			howToObtain: 'Found in Decorated Pots inside Trial Chambers.'
		},
		{
			name: '5',
			howToObtain: 'Combine 9 Disc Fragments from Ancient City Loot Chests'
		},
		{
			name: 'Relic',
			howToObtain: 'Found in Suspicious Gravel inside Trail Ruins'
		},
		{
			name: 'Precipice',
			howToObtain: 'Vault and Reward Chest Loot from Trial Chambers'
		},
		{
			name: 'Tears',
			howToObtain:
				'Kill a Ghast with its own Fireball (deflect the Fireball back at it) and it will drop the Disc'
		},
		{
			name: 'Lava Chicken',
			howToObtain:
				'Kill a Baby Zombie Riding a Chicken (the Baby Zombie must die before the Chicken)'
		},
		{
			name: 'Bounce',
			howToObtain:
				'Chest Minecart Loot From an Abandoned Mineshaft that Intersects With a Sulfur Cave Biome'
		}
	]);
</script>

<TitleDescription title="Music Discs" description="Music disc guide + tracker" />

{#each discs as disc (disc.name)}
	<ContentCard>
		<p class="content-name">{disc.name}</p>
		<p class="content-subtext"><b>How to obtain: </b> {disc.howToObtain}</p>
	</ContentCard>
{/each}
