<script lang="ts">
	export let tag: 'button' | 'a' = 'button';
	export let variant: 'primary' | 'secondary' | 'disabled' = 'primary';
	export let onClick: ((event: MouseEvent) => void) | undefined = undefined;
</script>

<svelte:element
	this={tag}
	class={`Button ${variant}`}
	{...$$restProps}
	on:click|preventDefault={onClick}
>
	<div class="Button-wrapper">
		<slot />
	</div>
</svelte:element>

<style lang="scss">
	.Button {
		display: inline-flex;
		justify-content: center;
		align-items: center;
		font-weight: 600;
		font-size: 1.6rem;
		gap: 12px;
		cursor: pointer;
		text-transform: uppercase;
		width: 100%;
		max-width: 265px;
		line-height: 13px;
		font-weight: 300;
		text-transform: uppercase;
		padding: 10px;
		transition: ease color 0.3s, ease background 0.3s;
		text-decoration: none;

		&-wrapper {
			position: relative;
			top: 1px;
			display: flex;
			align-items: center;
			justify-content: center;
			gap: 8px;
		}
	}

	.primary {
		border: 0;
		color: var(--primary-btn-color);
		background: var(--primary-btn-bg);
		border-radius: 10px;
		padding: 16px;
		box-shadow: 0 1px 3px rgb(0 34 54 / 7%), 0 2px 6px rgb(0 34 54 / 7%);
		@media (prefers-color-scheme: dark) {
			box-shadow: none;
			border-radius: 0px;
			padding: 10px;
		}

		@include down('md') {
			max-width: 315px;
		}

		&:hover {
			background: var(--primary-btn-bg-hover);
		}
	}

	[disabled] {
		cursor: default;
		background: grey;
		color: white;

		&:hover {
			background: grey;
			color: white;
		}
	}
</style>
