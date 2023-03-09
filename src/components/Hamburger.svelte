<script lang="ts">
	export let isMenuShowing: boolean = false;
</script>

<div
	class="Hamburger"
	class:active={isMenuShowing}
	on:click|preventDefault={() => {
		isMenuShowing = !isMenuShowing;
	}}
	on:keydown|preventDefault={() => {
		isMenuShowing = !isMenuShowing;
	}}
>
	<span class="Hamburger-stick" />
	<span class="Hamburger-stick" />
	<span class="Hamburger-stick" />
</div>

<style lang="scss">
	.Hamburger {
		position: relative;
		top: -1px;
		height: 20px;
		width: 30px;
		cursor: pointer;

		@include up('sm') {
			display: none;
		}

		&-stick {
			position: absolute;
			display: block;
			height: 2px;
			width: 30px;
			background: var(--link-color);
			transition: ease opacity 0.2s, ease transform 0.3s;

			&:nth-child(1) {
				top: 0;
			}

			&:nth-child(2) {
				top: 50%;
				transform: translateY(-50%);
			}

			&:nth-child(3) {
				bottom: 0;
			}
		}

		&.active {
			pointer-events: none;

			.Hamburger-stick {
				&:nth-child(1) {
					top: 0;
					transform: rotate(45deg) translate(7px, 6px);
				}

				&:nth-child(2) {
					opacity: 0;
				}

				&:nth-child(3) {
					transform: rotate(-45deg) translate(7px, -6px);
				}
			}
		}
	}
</style>
