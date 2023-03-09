<script lang="ts">
	import '../app.scss';
	import Container from '../components/Container.svelte';
	import Header from '../components/Header.svelte';
</script>

<main>
	<div class="Navigation">
		<Container>
			<Header />
		</Container>
	</div>
	<slot />
</main>

<style lang="scss">
	main {
		background: var(--background-bg);
		height: 100%;
		width: 100%;
		bakground: red;
		overflow: hidden;
	}

	.Navigation {
		background: var(--header-bg);
	}
</style>
