<script lang="ts">
	export let tag: 'h1' | 'h2' | 'h3' | 'h4' | 'h5' = 'h1';
	export let size: 'xs' | 'sm' | 'md' = 'md';
	export let weight: 'regular' | 'bold' = 'regular';
	export let align: 'center' | 'left' | 'right' = 'left';
	export let uppercase: boolean = false;
	export let block: boolean = false;
</script>

<svelte:element this={tag} class={`Title ${size} ${weight} ${align}`} class:uppercase class:block>
	<slot />
</svelte:element>

<style lang="scss">
	.Title {
		margin: 0;
		font-family: 'Madera', sans;
		color: var(--title-color);
	}

	// Sizes

	.md {
		font-size: 4rem;
		margin-bottom: 40px;
		@include down('md') {
			font-size: 2.7rem;
		}
	}

	// Align

	.block {
		width: 100%;
	}

	.center {
		text-align: center;
	}

	.left {
		text-align: left;
	}

	.right {
		text-align: right;
	}

	// Weight

	.regular {
		font-weight: 400;
	}

	.bold {
		font-weight: bold;
	}

	// Text Transform

	.uppercase {
		text-transform: uppercase;
	}
</style>
