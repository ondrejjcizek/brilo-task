<script lang="ts">
	import Button from '../components/Button.svelte';
	import Container from '../components/Container.svelte';
	import Section from '../components/Section.svelte';
	import Text from '../components/Text.svelte';
	import Title from '../components/Title.svelte';
</script>

<Section variant="regular">
	<Container>
		<div class="Hero">
			<div class="Hero-content">
				<Title uppercase>Jack Jackson</Title>
				<Text>
					What a bounder joseph stalin groomed sportacus testosterone trophy freestyle derek
					griffiths robot moustache derek griffiths groomed testosterone trophy marquess of
					queensbury freestyle joseph stalin robot moustache Nostrilis tickler sportacus what a
					bounder groomed?
				</Text>
				<Button tag="a" href="#">Learn More</Button>
			</div>
			<div class="Hero-image">
				<img
					src="images/profile-photo.jpg"
					srcset="images/profile-photo@2x.jpg 2x"
					alt="Jack Jackson"
					loading="lazy"
				/>
			</div>
		</div>
	</Container>
</Section>

<style lang="scss">
	.Hero {
		display: flex;
		justify-content: space-between;
		gap: 24px;

		@include down('md') {
			flex-direction: column-reverse;
		}

		&-content {
			margin-top: 48px;
			max-width: 550px;

			:global(p) {
				margin-bottom: 52px;
			}

			@include down('md') {
				margin-top: 0;
			}

			@include down('md') {
				margin: -93px auto 0;
				text-align: center;

				@include up('md') {
					margin: -80px auto 0;
				}
				:global(h1) {
					display: flex;
					justify-content: center;
					position: relative;
					z-index: 1;
					text-align: center;
					max-width: 250px;
					margin: 0 auto 40px;
					background: rgba(white, 0.2);
					border-radius: 10px;
					@media (prefers-color-scheme: dark) {
						border-radius: 0px;
					}
				}

				:global(p) {
					text-align: center;
					margin-bottom: 32px;

					@include down('sm') {
						max-width: 315px;
					}
				}
			}
		}

		&-image {
			position: relative;
			height: 422.5px;
			width: 100%;
			min-width: 315px;
			max-width: 315px;

			img {
				position: absolute;
				inset: 0;
				filter: saturate(0.65) opacity(0.75);
				object-fit: cover;
				height: 100%;
				width: 100%;
				border-radius: 10px;
				box-shadow: 0 1px 3px rgb(0 34 54 / 7%), 0 2px 6px rgb(0 34 54 / 7%);
				@media (prefers-color-scheme: dark) {
					border-radius: 0px;
				}

				@include down('sm') {
					transform: scaleX(-1);
				}
			}

			&:after {
				content: '';
				display: block;
				position: absolute;
				inset: 0;
				padding-bottom: calc(422.5 / 315 * 100%);
				height: 100%;
				width: 100%;
			}

			@include down('md') {
				margin: 0 auto;
			}
		}
	}
</style>
