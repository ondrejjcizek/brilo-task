<script lang="ts">
	//
</script>

<div class="CardWrapper">
	<slot />
</div>

<style lang="scss">
	.CardWrapper {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 32px;

		@include down('md') {
			grid-template-columns: repeat(2, 1fr);
		}

		@include down('sm') {
			grid-template-columns: repeat(1, 1fr);
			gap: 36px;
		}

		@media (prefers-color-scheme: dark) {
			border: 0.5px solid rgba(white, 0.5);
		}
	}
</style>
