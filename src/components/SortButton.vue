<!-- Sort order button component -->
<template>
	<button 
		class="sort__task--button"
		@click="toggleSort">
		Sort list
	</button>
 </template>
 
 <script>
	export default {
		methods: {
			toggleSort() {
				this.$emit('toggle-sort');
			}
		}
	};
 </script>

 <style>
	.sort__task--button {
		margin: var(--margin-small);
		padding: var(--padding-small);
		border: none;
		background: var(--color-background);
	}
</style>