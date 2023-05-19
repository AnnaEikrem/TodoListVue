<!-- Input Field component -->
<template>
	<!-- Form and label for better accessibility -->
	<form @submit.prevent="addTask">
		<label 
			class="task__input--label"
			for="newTaskInput">
			New Task
		</label>

			<input 
				class="task__input--value"
				v-model="newTask" 
				type="text" 
				placeholder="Enter a new task"
				id="newTaskInput">
	
			<add-button 
				@click="addTask">
			</add-button>
	</form>
</template>

<script>
	import AddButton from '../components/AddButton.vue';

	export default {
		data() {
			return {
				newTask: ''
			};
		},
		methods: {
			addTask() {
				if (this.newTask.trim() !== '') {
				this.$emit('task-added', this.newTask.trim());
				this.newTask = '';
				}
			}
		},
		components: {
			AddButton
		}
	};
</script>

<style scoped>
	form {
		display: flex;
		flex-direction: column;
	}

	/* .task__list--top {
		display: flex;
		flex-direction: column;
	} */

	.task__input--label {
		margin: var(--margin-small);
		text-align: center;
		font-size: 1.4rem;
		font-weight: 600;
	}
	.task__input--value {
		margin: var(--margin-small);
		padding: 0.5rem;
	}
</style>

