<script lang="ts">
	import TitleDescription from '#lib/components/TitleDescription.svelte';
	import ContentCard from '#lib/components/ContentCard.svelte';

	let hotkeys = $state([
		{ keys: 'Q', description: 'Drop a single item from a stack' },
		{ keys: 'CTRL + Q', description: 'Drop whole stack' },
		{ keys: 'F', description: 'Swap the item in your main hand with your off-hand' },

		{
			keys: 'SHIFT + Left Click',
			description:
				' Quickly transfer an item between your inventory and a chest (or equip armor directly)'
		},
		{
			keys: 'SHIFT + Double Click',
			description: 'Move all items of that specific type between your inventory and a chest'
		},
		{
			keys: 'Double Click an Item',
			description: 'Gather all items of that type into a single stack'
		},
		{ keys: 'Right Click', description: 'Pick up half of a stack' },
		{
			keys: 'Hover + Number Key',
			description: 'Send the hovered item directly to that hotbar slot'
		},
		{
			keys: 'Middle Click',
			description: 'Pull the block into your hotbar'
		},

		{ keys: 'F1', description: 'Toggle HUD' },
		{ keys: 'F2', description: 'Take a screenshot' },
		{ keys: 'F5', description: 'Change camera perspective' },
		{ keys: 'F11', description: 'Toggle full screen' },
		{ keys: 'F3 + A', description: 'Reload loaded chunks' },
		{ keys: 'F3 + B', description: 'Toggle hitboxes' },
		{
			keys: 'F3 + C',
			description: 'Copy current location (hold for 10 seconds to crash the game)'
		},
		{ keys: 'F3 + D', description: 'Clear chat history' },
		{ keys: 'F3 + G', description: 'Toggle chunk borders' },
		{ keys: 'F3 + H', description: 'Toggle advanced tooltips' },
		{ keys: 'F3 + N', description: 'Cycle between spectator and previous game mode' },
		{ keys: 'F3 + P', description: 'Toggle automatic game pause when the window loses focus' },
		{ keys: 'F3 + T', description: 'Reload resource packs without restarting the game' }
	]);
</script>

<TitleDescription title="Hotkeys" description="Hotkeys that will make you a better player" />

{#each hotkeys as hotkey (hotkey.keys)}
	<ContentCard>
		<p class="content-name">{hotkey.keys}</p>
		<p class="content-subtext">{hotkey.description}</p>
	</ContentCard>
{/each}
