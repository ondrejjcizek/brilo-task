<script lang="ts">
	import Text from './Text.svelte';
	import Title from './Title.svelte';
	export let imageSrc: string;
	export let imageAlt: string;
	export let link: string;
	export let title: string;
	export let text: string;
</script>

<a href={link} class="Card">
	<article>
		<div class="Card-image">
			<img
				src={`${imageSrc}.jpg`}
				srcset={`${imageSrc}@2x.jpg`}
				alt={imageAlt}
				loading="lazy"
				height="220"
				width="345"
			/>
		</div>
		<div class="Card-content">
			<Title tag="h3" size="xs" fontFamily="carmen" uppercase>{title}</Title>
			<Text size="sm">{text}</Text>
		</div>
	</article>
</a>

<style lang="scss">
	.Card {
		display: flex;
		flex-direction: column;
		background: var(--card-bg);
		text-decoration: none;
		border-radius: 10px;
		box-shadow: 0 1px 3px rgb(0 34 54 / 7%), 0 2px 6px rgb(0 34 54 / 7%);

		@media (prefers-color-scheme: dark) {
			border-radius: 0px;
			box-shadow: none;
		}

		&:hover {
			@include up('sm') {
				.Card {
					&-image {
						img {
							opacity: 1;
						}
					}

					&-content {
						transform: translateY(-5px);
					}
				}
			}
		}

		&-image {
			position: relative;

			&:before {
				content: '';
				display: block;
				position: absolute;
				inset: 0;
				padding-bottom: calc(220 / 345.34 * 100%);
				height: 100%;
				width: 100%;
			}

			&:after {
				position: absolute;
				inset: 0;
				top: 0px;
				content: '';
				display: block;
				border: 1px solid var(--card-border);
				margin: 24px;
				border-radius: 10px 10px 0 0;

				@media (prefers-color-scheme: dark) {
					top: 4px;
					border: 0.5px solid rgba(white, 0.5);
				}

				@media (prefers-color-scheme: dark) {
					top: -4px;
					border-radius: 0;
					margin: 12px 16px;
				}
			}

			img {
				width: 100%;
				height: 100%;
				opacity: 0.8;
				object-fit: cover;
				transition: ease opacity 0.3s;
				border-radius: 10px 10px 0 0;

				@media (prefers-color-scheme: dark) {
					border-radius: 0px;
				}
			}
		}

		&-content {
			padding: 32px 24px;
			transition: ease transform 0.3s;

			@media (prefers-color-scheme: dark) {
				padding: 32px 17px;
			}

			:global(h3) {
				color: var(--card-title-color);

				@media (prefers-color-scheme: dark) {
					color: rgb(255, 255, 255, 0.8);
				}
			}

			:global(p) {
				color: var(--card-text-color);

				@media (prefers-color-scheme: dark) {
					color: rgb(255, 255, 255, 0.8);
				}
			}
		}
	}
</style>
