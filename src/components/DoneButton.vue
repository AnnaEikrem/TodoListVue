<!-- Delete Button component -->
<!-- @click="$emit('click')">
{{ done ? 'Not done' : 'Done' }} -->

<template>
	<button 
		class="done__task--button" 
		@click="toggleDone">
		{{  done ? 'Not done' : 'Done' }}
	</button>
</template>

<script>
	export default {
		props: {
			done: {
				type: Boolean,
				required: true
			}
		},
		methods: {
			toggleDone() {
				this.$emit('update:done', !this.done);
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