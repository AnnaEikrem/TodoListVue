<!-- Delete Button component -->
<template>
	<button 
		class="done__task--button"
		@click="$emit('click')">{{ done ? 'Not done' : 'Done' }}
	</button>
</template>

<script>
	export default {
		props: {
			done: {
				type: Boolean,
				required: true
			}
		}
	};
</script>

<style>
	.done__task--button {
		margin: 0 var(--margin-small);
		padding: var(--padding-small);;
		background: var(--color-button);
		border: none;
	}
</style>