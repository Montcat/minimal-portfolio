<template>
	<div class="product-card">
		<a :href="project.html_url" target="_bl">
			<div class="card-layout">
				<h2 class="header">{{ ++index }} {{ project.name }}</h2>
				<p class="description">{{ project.description }}</p>
			</div>
		</a>
	</div>
</template>

<script setup>
	defineProps(["project", "index"]);
</script>

<style lang="scss" scoped>
	.card-layout {
		display: flex;
		flex-direction: column;
		margin: 1rem auto;
		gap: 0.5rem;
		background-color: var(--khaki-500);
		color: var(--color-theme-black-hex);
		border-radius: 1rem;
		padding: 1rem;

		.header {
			font-size: 1.5rem;
			font-weight: 600;
		}
	}
</style>
