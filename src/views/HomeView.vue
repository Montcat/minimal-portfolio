<template>
	<div class="home">
		<div class="profile-image-wrapper">
			<img :src="ProfileImage" alt="Profile Image" />
		</div>

		<div class="profile-content">
			<span class="name">Lamptey Sosthene</span>

			<span class="profession">A Frontend Developer</span>
		</div>
	</div>
</template>

<script setup>
	import ProfileImage from "@/assets/images/Montking.jpg";
</script>

<style lang="scss" scoped>
	.home {
		margin: auto;
		display: flex;
		flex-direction: column;
		place-items: center;

		.profile-image-wrapper {
			img {
				object-fit: contain;
				height: 10rem;
				width: 10rem;
				border-radius: 5rem;
			}
		}

		.profile-content {
			display: flex;
			flex-direction: column;
			place-items: center;

			.name {
				font-size: 2rem;
				font-weight: 700;
				display: flex;
				justify-content: center;
				padding: 1rem 0;
				text-align: center;
			}

			.profession {
				font-size: 1.2rem;
				margin: 1rem auto;
				text-align: center;
			}
		}
	}

	.name::after {
		content: "";
		width: 20%;
		height: 0;
		border: 1px solid;
		bottom: 0;
		position: absolute;
	}
</style>
