<script lang="ts">
	import Container from '../components/Container.svelte';
	import Section from '../components/Section.svelte';
</script>

<Section variant="regular" appended>
	<Container>
		<h1>Jack Jackson</h1>
		<p>
			What a bounder joseph stalin groomed sportacus testosterone trophy freestyle derek griffiths
			robot moustache derek griffiths groomed testosterone trophy marquess of queensbury freestyle
			joseph stalin robot moustache Nostrilis tickler sportacus what a bounder groomed?
		</p>
	</Container>
</Section>

<svelte:head>
	<title>Brilo Task</title>
</svelte:head>

<style lang="scss">
	h1 {
		color: $blue;
		font-size: 3.2rem;
	}

	p {
		font-size: 2rem;
	}

	//Up to tablet portrait - up to 991px
	@include down('lg') {
		h1 {
			color: red;
		}
	}
</style>
