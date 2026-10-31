<script lang="ts">
	import type { Snippet } from 'svelte';
	import type { HTMLButtonAttributes } from 'svelte/elements';

	interface ButtonProps extends HTMLButtonAttributes {
		children: Snippet;

		selected?: boolean;
	}

	let { children, selected, ...props }: ButtonProps = $props();
</script>

<button {...props} class:selected>
	{@render children()}
</button>

<style>
	button {
		padding: 0.5rem;
		background-color: var(--light);
		border: var(--border);
		box-shadow: var(--shadow);
		cursor: pointer;
		transition: 0.3s;
		user-select: none;
		&:hover {
			background-color: var(--highlight);
		}
	}
	.selected {
		background-color: var(--accent);
		&:hover {
			background-color: var(--accent);
		}
	}
</style>
