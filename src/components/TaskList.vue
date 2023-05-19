<!-- Task List component -->
<template>
	<ul class="tasks__list">
		<task-item
			v-for="task in sortedTasks"
			:key="task.text"
			:task="task"
			:done="task.done"
			@task-removed="removeTask"
			@update:done="toggleTask(task, $event)">
		</task-item>
	</ul>
</template>

<script>
	import TaskItem from './TaskItem.vue';

	export default {
		components: {
			TaskItem
		},
		props: {
			tasks: {
				type: Array,
				required: true
			}
		},
		computed: {
			sortedTasks() {
				return this.tasks.sort((a, b) => {
					const taskA = a.text.toLowerCase();
					const taskB = b.text.toLowerCase();
					if (taskA < taskB) return -1;
					if (taskA > taskB) return 1;
				return 0;
			});
		}},
		methods: {
		removeTask(task) {
			this.$emit('task-removed', task);
		},
		toggleTask(task, updatedDone) {
			task.done = updatedDone;
		}
		}
	};
</script>
