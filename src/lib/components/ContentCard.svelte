<script lang="ts">
	let { children } = $props();
</script>

<div class="content-card-main">
	<div class="content-wrapper">
		{@render children()}
	</div>
</div>

<style>
	.content-wrapper {
		display: flex;
		align-items: flex-start;
		justify-content: center;
		gap: 0.25rem;
		flex-direction: column;
		border: var(--border);
		margin-top: 0.5rem;
		padding: 0.5rem;
		background-color: var(--light);

		:global(.content-name) {
			text-transform: uppercase;
			font-size: 1rem;
			font-style: italic;
			font-weight: 600;
		}
		:global(.content-subtext) {
			color: var(--text-light);
		}
	}
</style>
