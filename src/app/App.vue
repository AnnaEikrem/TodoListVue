<!-- The main Todo list template -->
<template>
	<Header></Header>

	<section
		class="task__list--section">
		<input-field 
			@task-added="addTask">
		</input-field>

		<task-list
			:tasks="tasks"
			@task-removed="removeTask"
			@task-toggled="toggleTask">
		</task-list>
	</section>
</template>

<script>
	import Header from '../components/Header.vue';
	import InputField from '../components/InputField.vue';
	import TaskList from '../components/TaskList.vue';

	export default {
		components: {
			Header,
			InputField,
			TaskList
		},
		data() {
			return {
				tasks: []
			};
		},
		methods: {
			// Pushes 'task-input' as new Task in Tasks array
			addTask(task) {
				this.tasks.push({ text: task, done: false });
			},

			// Removes clicked Task in array, based on index
			removeTask(task) {
				const index = this.tasks.indexOf(task);
				if (index !== -1) {
				this.tasks.splice(index, 1);
			}
		},
			// Toggles class to mark as Done/not Done
//@task-toggled="toggleTask">

			toggleTask(task) {
				task.done = !task.done;
			}
		}
	};
</script>

<!-- Reset styling -->
<style>
@import '../style/main.css';

	* {
		box-sizing: border-box;
		padding: 0;
		margin: 0;
	}

	body {
		background: var(--color-light);
	}

	.task__list--section {
		margin: 2rem;
		padding: 2rem;
		background: var(--color-secondary);
		border-radius: 0.5rem;
	}

	@media screen and (min-width: 768px) {
		.task__list--section {
			margin: 2rem auto;
			width: 60vw;
		}
	}
</style> 
