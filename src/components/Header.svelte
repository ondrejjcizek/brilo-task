<script lang="ts">
	import Container from './Container.svelte';
</script>

<header>
	<Container>
		<nav>
			<ul>
				<li><a href="#todo">HOME</a></li>
				<li><a href="#todo">ABOUT ME</a></li>
				<li><a href="#todo">MY WORK</a></li>
			</ul>
		</nav>
	</Container>
</header>

<style lang="scss">
	header {
		background: $header-bg;
	}

	ul {
		display: flex;
		justify-content: flex-end;
		align-items: center;
		list-style-type: none;
		gap: 12px;
		font-size: 1.7rem;
		margin: 0;
		height: 72px;
	}

	li {
		height: 100%;
	}

	a {
		display: flex;
		align-items: center;
		text-decoration-color: transparent;
		color: rgba($white, 0.7);
		font-family: 'Madera', sans;
		letter-spacing: 3px;
		padding: 0 12px;
		height: 100%;
		transition: ease color 0.3s, ease text-decoration 0.3s;
		text-underline-offset: 8px;

		&:hover {
			color: $white;
			text-decoration-thickness: 0.75px;
			text-decoration-color: $white;
			text-underline-offset: 8px;
		}
	}
</style>
