<script lang="ts">
	export let variant: 'regular' = 'regular';
</script>

<div class={variant}>
	<slot />
</div>

<style lang="scss">
	div {
		position: relative;
		height: 100%;
		margin: 0 auto;
		padding: 0 36px;
		box-sizing: content-box;

		//Up to phone landscape - up to 767px
		@include up('md') {
			padding: 0 24px;
		}

		&.regular {
			max-width: 375px;

			@include up('md') {
				max-width: 1100px;
			}
		}
	}
</style>
