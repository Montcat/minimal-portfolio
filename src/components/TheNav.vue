<template>
	<div class="nav-container">
		<div class="link-item">
			<RouterLink :to="{ name: 'home' }">Home</RouterLink>
		</div>
		<div class="link-item">
			<RouterLink :to="{ name: 'about' }">About</RouterLink>
		</div>
		<div class="link-item">
			<RouterLink :to="{ name: 'projects' }">Projects</RouterLink>
		</div>
	</div>
</template>

<script setup>
	import { RouterLink } from "vue-router";
</script>

<style lang="scss" scoped>
	.nav-container {
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 2rem;
		margin-top: 2rem;

		.link-item {
			border: 2px solid var(--khaki-200);
			padding: 0.2rem 1rem;
			border-radius: 1rem;

			a {
				font-weight: 600;
			}
		}
	}
</style>
