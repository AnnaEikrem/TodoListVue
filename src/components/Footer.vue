<!-- Footer component -->
<template>
	<footer class="footer__container">	
			<div class="footer__creator">
				Made by {{ creator }}
			</div>

			<div class="footer__contact">
				<div class="footer__contact--email">
					{{ email }}
				</div>

				<div class="footer__contact--number">
					{{ phoneNumber}}
					</div>
			</div>
		</footer>
</template>
<script>
	export default {
		data() {
			return {
				creator: 'Anna Eikrem',
				phoneNumber: '46951735',
				email: 'eikrem.anna@gmail.com'
			}
		}
	}
</script>

<style>
	.footer__container {
		text-align: center;
		padding: var(--padding-basic);
		background: var(--color-background);
	}

	.footer__creator{
		font-weight: 700;
	}
</style>