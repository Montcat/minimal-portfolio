<template>
	<div class="app-container">
		<div class="app-content-wrapper">
			<!-- Navigation Section-->
			<div class="nav-section">
				<nav class="navigation">
					<TheNav />
				</nav>
			</div>

			<!-- View Section -->
			<main>
				<section class="view-container">
					<RouterView v-slot="{ Component }">
						<Transition name="fade" mode="out-in">
							<component :is="Component" />
						</Transition>
					</RouterView>
				</section>
			</main>

			<!-- Footer Section -->
			<footer>
				<TheFooter />
			</footer>
		</div>
	</div>
</template>

<script setup>
	import { RouterView } from "vue-router";
	import TheNav from "./components/TheNav.vue";
	import TheFooter from "./components/TheFooter.vue";
</script>

<style lang="scss" scoped>
	.app-content-wrapper {
		width: 65vw;
		margin: auto;

		.nav-section {
			margin: 2rem auto;
		}

		main {
			padding: 2rem 0;
			margin-bottom: 2rem;
		}
	}

	main:before {
		content: "";
		width: 100%;
		height: 0;
		border: 1px solid;
		position: absolute;
		top: 0;
		left: 0;
	}

	main:after {
		content: "";
		width: 100%;
		height: 0;
		border: 1px solid;
		position: absolute;
		bottom: 0;
		left: 0;
	}

	// Transition styles
	.fade-enter-from,
	.fade-leave-to {
		opacity: 0;
	}

	.fade-enter-active,
	.fade-leave-active {
		transition: opacity 0.5s ease-in-out;
	}
</style>
