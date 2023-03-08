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
				<Button tag="a" href="#todo">Learn More</Button>
			</div>
			<div class="Hero-image">
				<img src="images/profile-photo.jpg" srcset="images/profile-photo@2x.jpg 2x" alt="" />
			</div>
		</div>
	</Container>
</Section>

<style lang="scss">
	.Hero {
		display: flex;
		justify-content: space-between;
		gap: 24px;

		@include down('sm') {
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

			@include down('sm') {
				margin-top: -70px;
				text-align: center;

				:global(h1) {
					display: flex;
					justify-content: center;
					position: relative;
					z-index: 1;
					text-align: center;
					max-width: 250px;
					margin: 0 auto 40px;
					background: rgba(white, 0.3);
				}

				:global(p) {
					text-align: center;
					margin-bottom: 32px;
					padding: 0 24px;
				}
			}
		}

		&-image {
			img {
				aspect-ratio: 3/4;
				filter: saturate(0.65) opacity(0.75);

				@include down('md') {
					max-width: 250px;
				}
			}

			@include down('sm') {
				margin: 0 auto;
			}
		}
	}
</style>
