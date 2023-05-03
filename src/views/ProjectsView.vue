<template>
	<div class="projects">
		<h2 class="header">
			<span class="header-text">Projects from </span>
			<span class="icon"><IconGithub /></span>
		</h2>

		<div class="projects-content">
			<div v-if="loading" class="loader-wrapper">
				<TheLoader />
			</div>
			<div v-else>
				<div v-if="error">{{ error }}</div>
				<div v-for="(project, index) in projects" :key="project.id">
					<ProductCard :project="project" :index="index" />
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
	import IconGithub from "../components/icons/IconGithub.vue";
	import ProductCard from "@/components/ProductCard.vue";
	import TheLoader from "@/components/TheLoader.vue";
	import { ref, onMounted } from "vue";
	const projects = ref([]);
	const loading = ref(false);
	const error = ref(null);
	onMounted(async () => {
		try {
			loading.value = true;
			const res = await fetch("https://api.github.com/users/montcat/repos");
			projects.value = await res.json();
			loading.value = false;
		} catch (ex) {
			error.value = ex;
			loading.value = false;
		}
	});
</script>

<style lang="scss" scoped>
	.projects {
		.header {
			display: flex;
			height: 2rem;
			justify-content: center;
			align-items: center;
			gap: 0.5rem;
		}

		.icon {
			width: 2rem;
			fill: var(--khaki-200);
		}

		.projects-content {
			max-height: 80vh;
			overflow: scroll;
			border-radius: 1rem;
			padding: 0 1rem;
			margin-top: 2rem;
			border: 2px solid var(--khaki-400);

			/* Hide scrollbar for IE, Edge and Firefox */
			-ms-overflow-style: none; /* IE and Edge */
			scrollbar-width: none; /* Firefox */

			.loader-wrapper {
				margin: 1rem auto;
			}
		}
		/* Hide scrollbar for Chrome, Safari and Opera */
		.projects-content::-webkit-scrollbar {
			display: none;
		}
	}
</style>
