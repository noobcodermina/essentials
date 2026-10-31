<script lang="ts">
	let { title, description } = $props();
</script>

<div class="title-description-wrapper">
	<h2>{title}</h2>
	<p>{description}</p>
</div>

<style>
	.title-description-wrapper {
		margin-top: 2rem;
		margin-bottom: 2rem;
		h2 {
			text-transform: uppercase;
			color: var(--text);
			font-weight: 500;
			font-size: 1.25rem;
			font-style: italic;
		}
		p {
			margin-top: 0.25rem;
			color: var(--text-light);
		}
	}
</style>
