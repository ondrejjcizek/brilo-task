<script lang="ts">
	import { clickOutside } from '../actions/ClickOutside';
	import Container from './Container.svelte';
	import Hamburger from './Hamburger.svelte';
	import Navigation from './Navigation.svelte';
	let isMenuShowing: boolean = false;
</script>

<header>
	<Container>
		<Navigation />
	</Container>
</header>

<style lang="scss">
	header {
		position: relative;
		background: var(--header-bg);
		height: 72px;
	}
</style>
