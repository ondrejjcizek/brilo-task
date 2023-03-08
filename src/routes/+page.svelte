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
				<Button>Learn More</Button>
			</div>
			<div class="Hero-image">
				<img src="images/profile-photo.jpg" srcset="images/profile-photo@2x.jpg 2x" alt="" />
			</div>
		</div>
	</Container>
</Section>

<svelte:head>
	<title>Brilo Task</title>
</svelte:head>

<style lang="scss">
	.Hero {
		display: flex;
		justify-content: space-between;
		gap: 24px;

		&-content {
			margin-top: 48px;
			max-width: 550px;

			:global(p) {
				margin-bottom: 52px;
			}
		}

		&-wrapper {
			//
		}
	}
</style>
