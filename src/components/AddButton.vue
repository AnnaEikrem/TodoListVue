<!-- Add Button component -->
<template>
	<button class="add__task--button"
		@click="addTask">
		Add task
	</button>
</template>

<script>
	export default {
		methods: {
			addTask() {
				console.log('Add button clicked')
			}
		}
	}
</script>

<style scoped>
	.add__task--button {
		margin: var(--margin-small);
		padding: var(--padding-small);
		border: none;
		background: var(--color-button);
	}
</style>
