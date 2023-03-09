<script lang="ts">
	import '../app.scss';
	import Header from '../components/Header.svelte';
</script>

<main>
	<Header />
	<slot />
</main>

<style lang="scss">
	main {
		background: var(--primary-bg);
		height: 100%;
		width: 100%;
		bakground: red;
		overflow: hidden;
	}
</style>
