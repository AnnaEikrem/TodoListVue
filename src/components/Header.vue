<!-- Header component -->
<template>
	<header class="header__container">	
		<h1 class="header__headline"> 
			{{ headline }} 
		</h1>
	</header>
</template>

<script>
	export default {
		data() {
			return {
				headline: 'Plan ahead'
			}
		}
	}
</script>

<style>
	.header__container {
		text-align: center;
		padding: var(--padding-basic);
		background: var(--color-background);
	}

	.header__headline {
		color: var(--color-dark);
	}
</style>