<script lang="ts">
	export let tag: 'h1' | 'h2' | 'h3' | 'h4' | 'h5' = 'h1';
	export let size: 'xs' | 'sm' | 'md' = 'md';
	export let weight: 'regular' | 'bold' = 'regular';
	export let align: 'center' | 'left' | 'right' = 'left';
	export let fontFamily: 'madera' | 'carmen' = 'madera';
	export let uppercase: boolean = false;
	export let block: boolean = false;
</script>

<svelte:element
	this={tag}
	class={`Title ${size} ${weight} ${align} ${fontFamily}`}
	class:uppercase
	class:block
>
	<slot />
</svelte:element>

<style lang="scss">
	.Title {
		margin: 0;
		color: var(--title-color);
	}

	// Sizes

	.xs {
		font-size: 2.1rem;
		margin-bottom: 24px;

		@include down('lg') {
			font-size: 1.8rem;
		}

		@include down('md') {
			font-size: 1.8rem;
			margin-bottom: 16px;
		}

		@include down('sm') {
			margin-bottom: 12px;
		}
	}

	.sm {
		font-size: 2.8rem;
		margin-bottom: 24px;
		line-height: 28px;

		@include down('md') {
			font-size: 2.4rem;
			line-height: 24px;
			margin-bottom: 36px;
		}

		@media (prefers-color-scheme: dark) {
			color: rgb(255, 255, 255, 0.8);
		}
	}

	.md {
		font-size: 4.5rem;
		line-height: 45px;
		margin-bottom: 40px;

		@include down('md') {
			font-size: 3rem;
		}

		@media (prefers-color-scheme: dark) {
			color: rgb(255, 255, 255, 0.8);
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

	// Font Family

	.madera {
		font-family: 'Madera', sans-serif;
	}

	.carmen {
		font-family: 'Carmen', sans-serif;
	}
</style>
