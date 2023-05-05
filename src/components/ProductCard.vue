<template>
	<div class="product-card">
		<a :href="project.htmlUrl" target="_bl">
			<div class="card-layout">
				<h2 class="header">{{ project.name }}</h2>
				<p class="description">{{ project.description }}</p>
				<span class="live-preview">
					<a :href="project.livePreviewUrl" target="_bl">{{ project.livePreviewUrl }}</a>
				</span>
			</div>
		</a>
	</div>
</template>

<script setup>
	defineProps(["project"]);
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

		.live-preview > a {
			color: var(--color-theme-black-hex);
		}
	}
</style>
