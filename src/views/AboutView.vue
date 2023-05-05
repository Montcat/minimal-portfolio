<template>
	<div class="about">
		<div class="about-content">
			<h2 class="header">Hi, I'm Lamptey Sosthene</h2>

			<p>
				Passionate about Frontend Development, I'm expanding my knowledge by
				mastering JavaScript with VueJs. With a keen eye for detail and a
				commitment to excellence, I create captivating and user-friendly web
				applications. Let's build something amazing together!
			</p>

			<div class="tags">
				<span class="tag-item">
					<a href="#" class="tag-language">JavaScript</a>
				</span>
				<span class="tag-item">
					<a href="#" class="tag-language">VueJs</a>
				</span>
			</div>
		</div>
	</div>
</template>

<script setup></script>

<style lang="scss" scoped>
	.about-content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		.header {
			font-weight: 700;
			font-size: 2rem;
			text-align: center;
			margin: auto;
		}

		p {
			text-align: center;
			padding: 1rem 2vw;
		}

		.tags {
			display: flex;
			gap: 2rem;

			.tag-item > a {
				color: var(--khaki-400);
			}
		}
	}

	.tag-language::before {
		content: "☯";
		opacity: 0;
		transition: 700ms;
	}

	.tag-language:hover::before {
		opacity: 1;
	}
</style>
