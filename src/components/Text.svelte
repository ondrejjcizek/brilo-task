<script lang="ts">
	import { createEventDispatcher } from 'svelte';

	export let tag: 'span' | 'p' | 'div' = 'p';
	export let size: 'xs' | 'sm' | 'md' | 'lg' | 'xl' = 'md';
	export let weight: 'regular' | 'medium' | 'semiBold' = 'regular';
	export let align: 'left' | 'right' | 'center' = 'left';
	export let block: boolean = false;
	export let textTranform: 'uppercase' | 'lowercase' | 'defaultcase' = 'defaultcase';
</script>

<svelte:element
	this={tag}
	class={`Text ${size} ${weight} ${align} ${textTranform}`}
	class:block
	{...$$restProps}
>
	<slot />
</svelte:element>

<style lang="scss">
	.Text {
		position: relative;
		margin: 0;
		color: var(--text-color);
	}

	.block {
		display: block;
		width: 100%;
	}

	// Sizes

	.sm {
		font-size: 1.5rem;
		line-height: 1.33;
	}

	.md {
		font-size: 1.7rem;
		line-height: 1.33;

		@include down('md') {
			font-size: 1.6rem;
		}
	}

	// Weight

	.regular {
		font-weight: normal;
	}

	.medium {
		font-weight: 500;
	}

	.semiBold {
		font-weight: 600;
	}

	// Align

	.left {
		text-align: left;
	}

	.right {
		text-align: right;
	}

	.center {
		text-align: center;
	}

	// Text Transform

	.uppercase {
		text-transform: uppercase;
	}

	.lowercase {
		text-transform: lowercase;
	}

	// Text Decoration

	.underline {
		text-decoration: underline;
	}

	.no-underline {
		text-decoration: none;
	}
</style>
