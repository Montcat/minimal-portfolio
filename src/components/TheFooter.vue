<template>
	<div class="footer">
		<a
			href="https://www.linkedin.com/in/sosthene-lamptey-55b7b8191/"
			target="_blank"
			class="link-item"
		>
			<IconLinkedIn />
		</a>
		<a
			href="https://web.facebook.com/montcat.sosthene"
			target="_blank"
			class="link-item"
		>
			<IconFacebook />
		</a>
		<a href="https://github.com/Montcat" target="_blank" class="link-item">
			<IconGithub />
		</a>
		<a href="mailto: montcat99@gmail.com" target="_blank" class="link-item">
			<IconEmail />
		</a>
	</div>
</template>

<script setup>
	import IconLinkedIn from "./icons/IconLinkedIn.vue";
	import IconGithub from "./icons/IconGithub.vue";
	import IconFacebook from "./icons/IconFacebook.vue";
	import IconEmail from "./icons/IconEmail.vue";
</script>

<style lang="scss" scoped>
	.footer {
		display: flex;
		place-content: center;
		gap: 2rem;

		.link-item {
			width: 2rem;
			fill: var(--khaki-200);
		}
	}
</style>
