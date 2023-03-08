<script>
	import Container from '../components/Container.svelte';
	import Text from '../components/Text.svelte';
</script>

<footer>
	<Container>
		<Text align="center">© Jack Jackson 2020</Text>
	</Container>
</footer>

<style lang="scss">
	footer {
		margin-bottom: 72px;

		@include down('md') {
			margin-bottom: 66px;
		}
	}
</style>
