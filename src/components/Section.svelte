<script lang="ts">
	export let variant: 'regular' = 'regular';
	export let prepended: boolean = false;
	export let appended: boolean = false;
</script>

<section class={variant} class:prepended class:appended>
	<slot />
</section>

<style lang="scss">
	section {
		&.regular {
			padding: 80px 0;
		}

		@include up('md') {
			&.regular {
				padding: 160px 0;
			}
		}

		@include up('lg') {
			&.regular {
				padding: 240px 0;
			}
		}

		&.prepended {
			padding-bottom: 0;
		}

		&.appended {
			padding-top: 0;
		}
	}
</style>
