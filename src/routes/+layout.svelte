<script lang="ts">
	import '../app.scss';
	import Header from '../components/Header.svelte';
</script>

<Header />

<main>
	<slot />
</main>

<style lang="scss">
	main {
		background: var(--primary-bg);
		height: 100%;
	}
</style>
