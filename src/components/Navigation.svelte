<script lang="ts">
	import { clickOutside } from '../actions/ClickOutside';
	import Hamburger from './Hamburger.svelte';
	export let isMenuShowing: boolean = false;
</script>

<nav>
	<ul
		use:clickOutside={() => {
			isMenuShowing = false;
		}}
		class:active={isMenuShowing}
	>
		<li><a href="#">HOME</a></li>
		<li><a href="#">ABOUT ME</a></li>
		<li><a href="#">MY WORK</a></li>
	</ul>
	<Hamburger bind:isMenuShowing />
</nav>

<style lang="scss">
	nav {
		display: flex;
		align-items: center;
		justify-content: flex-end;
		position: absolute;
		right: 20px;
		top: 50%;
		transform: translateY(-50%);
		height: 100%;
		z-index: 1;
		min-width: 100%;
		right: 0;

		@include up('sm') {
			position: absolute;
			top: 0;
			left: 50%;
			transform: translateX(-50%);
		}
	}

	ul {
		display: flex;
		justify-content: center;
		align-items: center;
		list-style-type: none;
		gap: 12px;
		font-size: 1.7rem;
		margin: 0;
		padding-left: 0;
		height: 72px;
		transition: ease transform 0.3s;
		overflow: hidden;

		@include down('sm') {
			display: flex;
			position: absolute;
			background: var(--header-bg);
			right: -2px;
			gap: 40px;
			top: 90px;
			width: 200px;
			height: fit-content;
			flex-direction: column;
			padding: 32px;
			border-radius: 10px;
			transform: translateX(340px);
			box-shadow: 0 1px 1px hsl(0deg 0% 0% / 0.075), 0 2px 2px hsl(0deg 0% 0% / 0.075),
				0 4px 4px hsl(0deg 0% 0% / 0.075), 0 8px 8px hsl(0deg 0% 0% / 0.075),
				0 16px 16px hsl(0deg 0% 0% / 0.075);
		}
		&.active {
			transform: translateX(24px);
		}

		@include up('md') {
			justify-content: flex-end;
		}
	}

	li {
		height: 100%;
	}

	a {
		display: flex;
		align-items: center;
		text-decoration-color: transparent;
		color: var(--link-color);
		font-family: 'Madera', sans;
		letter-spacing: 3px;
		padding: 0 12px;
		height: 100%;
		transition: ease color 0.3s, ease text-decoration 0.3s;
		text-underline-offset: 8px;
		white-space: nowrap;

		@media (prefers-color-scheme: dark) {
			font-weight: 400;
		}

		@include up('up') {
			text-decoration: none;
		}

		@include up('md') {
			@media (prefers-color-scheme: dark) {
				font-weight: bold;
			}
		}

		&:hover {
			color: var(--link-hover-color);
			text-decoration-thickness: 0.75px;
			text-decoration-color: var(--text-color);
			text-underline-offset: 8px;

			@include down('sm') {
				text-decoration: none;
			}
		}
	}
</style>
