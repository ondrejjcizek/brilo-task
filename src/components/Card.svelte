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
			<img src={`${imageSrc}.jpg`} srcset={`${imageSrc}@2x.jpg`} alt={imageAlt} />
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

			&:after {
				position: absolute;
				inset: 0;
				top: -3px;
				content: '';
				display: block;
				border: 0.5px solid rgba(white, 0.5);
				margin: 12px 16px;
			}

			img {
				width: 100%;
				opacity: 0.8;
				aspect-ratio: 173/110;
				transition: ease opacity 0.3s;
			}
		}

		&-content {
			padding: 32px 16px;
			transition: ease transform 0.3s;

			:global(h3) {
				color: var(--card-title-color);
			}

			:global(p) {
				color: var(--card-text-color);
			}
		}
	}
</style>
