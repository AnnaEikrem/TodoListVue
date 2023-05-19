<!-- Delete Button component -->
<template>
	<button 
		class="delete__task--button"
		@click="$emit('click')">
		Delete
	</button>
 </template>

<style>
	.delete__task--button {
		margin: 0 0.5rem;
		padding: var(--padding-small);
		background: var(--color-primary);
		border: none;
	}
</style>