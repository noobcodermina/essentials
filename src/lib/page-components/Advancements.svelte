<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';
	import ContentCard from '#lib/components/ContentCard.svelte';
	let advancements = $state([
		{
			name: 'Stone Age',
			howToObtain: 'Have Cobblestone, Blackstone or Cobbled Deepslate in your inventory'
		},
		{
			name: 'Getting an Upgrade',
			howToObtain: 'Obtain stone pickaxe'
		},
		{
			name: 'Acquire Hardware',
			howToObtain: 'Obtain iron ingot'
		},
		{
			name: 'Suit Up',
			howToObtain: 'Obtain any piece of iron armor'
		},
		{
			name: 'Hot Stuff',
			howToObtain: 'Fill a bucket with lava'
		},
		{
			name: "Isn't It Iron Pick?",
			howToObtain: 'Obtain iron pickaxe'
		},
		{
			name: 'Not Today, Thank You',
			howToObtain: 'Block any projectile with a shield'
		},
		{
			name: 'Ice Bucket Challenge',
			howToObtain: 'Obtain obsidian'
		},
		{
			name: 'Diamonds!',
			howToObtain: 'Obtain diamond'
		},
		{
			name: 'We Need to Go Deeper',
			howToObtain: 'Go to nether'
		},
		{
			name: 'Cover Me with Diamonds',
			howToObtain: 'Obtain any piece of diamond armor'
		},
		{
			name: 'Enchanter',
			howToObtain: 'Enchant any item'
		},
		{
			name: 'Zombie Doctor',
			howToObtain: 'Cure a zombie villager'
		},
		{
			name: 'Eye Spy',
			howToObtain: 'Enter the stronghold'
		},
		{
			name: 'The End?',
			howToObtain: 'Go to the end'
		},

		// Nether
		{
			name: 'Return to Sender',
			howToObtain: 'Kill a ghast with its own fireball'
		},
		{
			name: 'Those Were the Days',
			howToObtain: 'Enter a bastion remnant'
		},
		{
			name: 'Hidden in the Depths',
			howToObtain: 'Obtain ancient debris'
		},
		{
			name: 'Subspace Bubble',
			howToObtain: 'Travel 7000 blocks between two overworld locations through the nether'
		},
		{
			name: 'A Terrible Fortress',
			howToObtain: 'Enter a nether fortress'
		},
		{
			name: 'Who is Cutting Onions?',
			howToObtain: 'Obtain crying obsidian'
		},
		{
			name: 'Oh Shiny',
			howToObtain: 'Distract a piglin with gold'
		},
		{
			name: 'This Boat Has Legs',
			howToObtain: 'Ride a strider with a warped fungus on a stick'
		},
		{
			name: 'Uneasy Alliance',
			howToObtain: 'Bring a ghast to the overworld and kill it'
		},
		{
			name: 'War Pigs',
			howToObtain: 'Loot a chest in a bastion remnant'
		},
		{
			name: 'Cover Me in Debris',
			howToObtain: 'Obtain a full set of netherite armor'
		},
		{
			name: 'Spooky Scary Skeleton',
			howToObtain: 'Obtain wither skeleton skull'
		},
		{
			name: 'Into Fire',
			howToObtain: 'Obtain blaze rod'
		},
		{
			name: 'Not Quite "Nine" Lives',
			howToObtain: 'Fully charge a respawn anchor'
		},
		{
			name: 'Feels Like Home',
			howToObtain: 'Ride a strider for 50 blocks on lava in the overworld'
		},
		{
			name: 'Hot Tourist Destinations',
			howToObtain: 'Visit every nether biome'
		},
		{
			name: 'Withering Heights',
			howToObtain: 'Summon the wither'
		},
		{
			name: 'Local Brewery',
			howToObtain: 'Brew a potion'
		},
		{
			name: 'Bring Home the Beacon',
			howToObtain: 'Build and activate a beacon'
		},
		{
			name: 'A Furious Cocktail',
			howToObtain: 'Have every required potion effect at once'
		},
		{
			name: 'Beaconator',
			howToObtain: 'Activate a full-power beacon'
		},
		{
			name: 'How Did We Get Here?',
			howToObtain: 'Have every status effect at once'
		},

		// The End
		{
			name: 'Free the End',
			howToObtain: 'Kill the ender dragon'
		},
		{
			name: 'The Next Generation',
			howToObtain: 'Obtain the dragon egg'
		},
		{
			name: 'Remote Getaway',
			howToObtain: 'Enter an end gateway'
		},
		{
			name: 'The End... Again...',
			howToObtain: 'Respawn the ender dragon'
		},
		{
			name: 'You Need a Mint',
			howToObtain: 'Collect dragon breath in a bottle'
		},
		{
			name: 'The City at the End of the Game',
			howToObtain: 'Enter an end city'
		},
		{
			name: "Sky's the Limit",
			howToObtain: 'Obtain elytra'
		},
		{
			name: 'Great View From Up Here',
			howToObtain: 'Levitate 50 blocks using a shulker attack'
		},

		// Adventure
		{
			name: 'Heart Transplanter',
			howToObtain: 'Place a creaking heart between two pale oak logs'
		},
		{
			name: 'Voluntary Exile',
			howToObtain: 'Kill a raid captain'
		},
		{
			name: 'Country Lode, Take Me Home',
			howToObtain: 'Use a compass on a lodestone'
		},
		{
			name: 'Is It a Bird?',
			howToObtain: 'Look at a parrot through a spyglass'
		},
		{
			name: 'Monster Hunter',
			howToObtain: 'Kill a hostile mob'
		},
		{
			name: 'The Power of Books',
			howToObtain: 'Read a chiseled bookshelf with a comparator'
		},
		{
			name: 'What a Deal!',
			howToObtain: 'Trade with a villager'
		},
		{
			name: 'Crafting a New Look',
			howToObtain: 'Trim armor at a smithing table'
		},
		{
			name: 'Sticky Situation',
			howToObtain: 'Slide down a honey block'
		},
		{
			name: "Ol' Betsy",
			howToObtain: 'Shoot a crossbow'
		},
		{
			name: 'Surge Protector',
			howToObtain: 'Protect a villager from lightning using a lightning rod'
		},
		{
			name: 'Caves & Cliffs',
			howToObtain: 'Fall from the top to the bottom of the world and survive'
		},
		{
			name: 'Respecting the Remnants',
			howToObtain: 'Brush suspicious sand or gravel to obtain a pottery sherd'
		},
		{
			name: 'Sneak 100',
			howToObtain: 'Sneak near a sculk sensor or warden'
		},
		{
			name: 'Sweet Dreams',
			howToObtain: 'Sleep in a bed'
		},
		{
			name: 'Hero of the Village',
			howToObtain: 'Win a village raid'
		},
		{
			name: 'Is It a Balloon?',
			howToObtain: 'Look at a ghast through a spyglass'
		},
		{
			name: 'A Throwaway Joke',
			howToObtain: 'Hit a mob with a thrown trident'
		},
		{
			name: 'It Spreads',
			howToObtain: 'Kill a mob near a sculk catalyst'
		},
		{
			name: 'Take Aim',
			howToObtain: 'Shoot a mob with an arrow'
		},
		{
			name: 'Monsters Hunted',
			howToObtain: 'Kill every hostile mob'
		},
		{
			name: 'Postmortal',
			howToObtain: 'Use a totem of undying to survive fatal damage'
		},
		{
			name: 'Mob Kabob',
			howToObtain: 'Hit five mobs with one spear charge attack'
		},
		{
			name: 'Hired Help',
			howToObtain: 'Summon an iron golem'
		},
		{
			name: 'Star Trader',
			howToObtain: 'Trade with a villager above Y=318'
		},
		{
			name: 'Smithing with Style',
			howToObtain: 'Use all eight required armor trim templates'
		},
		{
			name: 'Two Birds, One Arrow',
			howToObtain: 'Kill two phantoms with one piercing arrow'
		},
		{
			name: "Who's the Pillager Now?",
			howToObtain: 'Kill a pillager with a crossbow'
		},
		{
			name: 'Arbalistic',
			howToObtain: 'Kill five different mobs with one crossbow shot'
		},
		{
			name: 'Careful Restoration',
			howToObtain: 'Craft a decorated pot using four pottery sherds'
		},
		{
			name: 'Adventuring Time',
			howToObtain: 'Visit every overworld biome'
		},
		{
			name: 'Sound of Music',
			howToObtain: 'Play a music disc in a meadow biome'
		},
		{
			name: 'Light as a Rabbit',
			howToObtain: 'Walk on powder snow wearing leather boots'
		},
		{
			name: 'Is It a Plane?',
			howToObtain: 'Look at the ender dragon through a spyglass'
		},
		{
			name: 'Very Very Frightening',
			howToObtain: 'Strike a villager with lightning from a trident'
		},
		{
			name: 'Sniper Duel',
			howToObtain: 'Kill a skeleton from at least 50 blocks away'
		},
		{
			name: 'Bullseye',
			howToObtain: 'Hit the center of a target from 30 blocks away'
		},
		{
			name: "Isn't It Scute?",
			howToObtain: 'Brush an armadillo to obtain armadillo scutes'
		},
		{
			name: 'Minecraft: Trial(s) Edition',
			howToObtain: 'Enter a trial chamber'
		},
		{
			name: 'Crafters Crafting Crafters',
			howToObtain: 'Be near a crafter when it crafts another crafter'
		},
		{
			name: 'Lighten Up',
			howToObtain: 'Scrape an oxidized copper bulb with an axe'
		},
		{
			name: 'Who Needs Rockets?',
			howToObtain: 'Use a wind charge to launch yourself 8 blocks up'
		},
		{
			name: 'Under Lock and Key',
			howToObtain: 'Unlock a vault with a trial key'
		},
		{
			name: 'Revaulting',
			howToObtain: 'Unlock an ominous vault with an ominous trial key'
		},
		{
			name: 'Blowback',
			howToObtain: 'Kill a breeze with its own wind charge'
		},
		{
			name: 'Over-Overkill',
			howToObtain: 'Deal 50 hearts of damage in one hit with a mace'
		},

		// Husbandry

		{
			name: 'Stay Hydrated!',
			howToObtain: 'Place a dried ghast in water'
		},
		{
			name: 'Bee Our Guest',
			howToObtain: 'Collect honey with a bottle without angering bees'
		},
		{
			name: 'The Parrots and the Bats',
			howToObtain: 'Breed two animals'
		},
		{
			name: "You've Got a Friend in Me",
			howToObtain: 'Have an allay bring items to you'
		},
		{
			name: 'Whatever Floats Your Goat!',
			howToObtain: 'Ride in a boat with a goat'
		},
		{
			name: 'Best Friends Forever',
			howToObtain: 'Tame an animal'
		},
		{
			name: 'Glow and Behold!',
			howToObtain: 'Make a sign glow using a glow ink sac'
		},
		{
			name: 'Fishy Business',
			howToObtain: 'Catch a fish'
		},
		{
			name: 'Total Beelocation',
			howToObtain: 'Move a bee nest with three bees using silk touch'
		},
		{
			name: 'Bukkit Bukkit',
			howToObtain: 'Catch a tadpole in a bucket'
		},
		{
			name: 'Uh-Oh',
			howToObtain: 'Have a sulfur cube absorb TNT'
		},
		{
			name: 'Smells Interesting',
			howToObtain: 'Obtain a sniffer egg'
		},
		{
			name: 'A Seedy Place',
			howToObtain: 'Plant a seed'
		},
		{
			name: 'Wax On',
			howToObtain: 'Wax a copper block using honeycomb'
		},
		{
			name: 'Two by Two',
			howToObtain: 'Breed every required animal'
		},
		{
			name: 'Birthday Song',
			howToObtain: 'Have an allay drop a cake on a note block'
		},
		{
			name: 'A Complete Catalogue',
			howToObtain: 'Tame every cat variant'
		},
		{
			name: 'Tactical Fishing',
			howToObtain: 'Catch a fish using a water bucket'
		},
		{
			name: 'When the Squad Hops into Town',
			howToObtain: 'Put every frog variant on a lead'
		},
		{
			name: 'Little Sniffs',
			howToObtain: 'Feed a snifflet torchflower seeds'
		},
		{
			name: 'A Balanced Diet',
			howToObtain: 'Eat every required food'
		},
		{
			name: 'Serious Dedication',
			howToObtain: 'Obtain a netherite hoe'
		},
		{
			name: 'Wax Off',
			howToObtain: 'Remove wax from a copper block using an axe'
		},
		{
			name: 'The Cutest Predator',
			howToObtain: 'Catch an axolotl in a bucket'
		},
		{
			name: 'With Our Powers Combined!',
			howToObtain: 'Obtain all three froglight types'
		},
		{
			name: 'Planting the Past',
			howToObtain: 'Plant torchflower seeds or a pitcher pod'
		},
		{
			name: 'The Healing Power of Friendship!',
			howToObtain: 'Help an axolotl win a fight'
		},
		{
			name: 'Good as New',
			howToObtain: 'Fully repair wolf armor using armadillo scutes'
		},
		{
			name: 'The Whole Pack',
			howToObtain: 'Tame every wolf variant'
		},
		{
			name: 'Shear Brilliance',
			howToObtain: 'Remove wolf armor using shears'
		}
	]);
</script>

<TitleDescription title="Advancements" description="List of every advancement + tracker" />

{#each advancements as advancement (advancement.name)}
	<ContentCard>
		<p class="content-name">{advancement.name}</p>
		<p class="content-subtext">{advancement.howToObtain}</p>
	</ContentCard>
{/each}

<style>
</style>
