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
				<div v-for="project in projects" :key="project.id">
					<ProductCard :project="project" />
				</div>
			</div>
		</div>
		<span class="scroll-notifyer">Scroll form more</span>
	</div>
</template>

<script setup>
	import IconGithub from "../components/icons/IconGithub.vue";
	import ProductCard from "@/components/ProductCard.vue";
	import TheLoader from "@/components/TheLoader.vue";
	import { ref } from "vue";

	// The loading ref has no effect at the moment because i indended on fetching the repos from github but since github can't deploy ssg pages
	const loading = ref(false);
	const projects = ref([
		{
			name: "Result Summary Component - VueJs",
			htmlUrl: "https://github.com/Montcat/vue-result-summary-component",
			description:
				"This project is a solution to one of the challenges from frontend mentor",
			livePreviewUrl: "https://montcat.github.io/vue-result-summary-component/",
		},
		{
			name: "Intro Dropdown Navigation - VueJs",
			htmlUrl: "https://github.com/Montcat/intro-dropdown-navigation",
			description:
				"This project is a solution to one of the challenges from frontend mentor",
			livePreviewUrl: "https://montcat.github.io/intro-dropdown-navigation/",
		},
		{
			name: "News Homepage - VueJs",
			htmlUrl: "https://github.com/Montcat/news-homepage",
			description:
				"This project was a solution to one of the challenges from frontend mentor",
			livePreviewUrl: "https://montcat.github.io/news-homepage/",
		},
		{
			name: "Expenses Chart Component - VueJs",
			htmlUrl: "https://github.com/Montcat/expenses-chart",
			description:
				"This project was a solution to one of the challenges from frontend mentor",
			livePreviewUrl: "https://montcat.github.io/expenses-chart/",
		},
	]);
</script>

<style lang="scss" scoped>
	.projects {
		display: flex;
		flex-direction: column;
		align-items: center;
		.header {
			display: flex;
			height: 2rem;
			justify-content: center;
			align-items: center;
			gap: 0.5rem;
		}

		.header-text {
			font-weight: 600;
		}

		.icon {
			width: 2rem;
			fill: var(--khaki-200);
		}

		.projects-content {
			max-height: 90vh;
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

		.scroll-notifyer {
			font-weight: 600;
		}
	}
</style>
