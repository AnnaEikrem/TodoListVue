<!-- Task List component -->
<template>
	<ul class="tasks__list">
		<sort-button
			@toggle-sort="toggleSort">
		</sort-button>

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
	import SortButton from './SortButton.vue';
	import TaskItem from './TaskItem.vue';

	export default {
		components: {
			SortButton,
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
      		const sorted = [...this.tasks];
      		sorted.sort((a, b) => {
        			const taskA = a.text.toLowerCase();
        			const taskB = b.text.toLowerCase();
        			if (this.ascendingSort) {
          		if (taskA < taskB) return -1;
          		if (taskA > taskB) return 1;
        		} else {
          		if (taskA < taskB) return 1;
          		if (taskA > taskB) return -1;
        		}
        	return 0;
      });
      return sorted;
    }
	},
		methods: {
		removeTask(task) {
			this.$emit('task-removed', task);
		},
		toggleTask(task, updatedDone) {
			task.done = updatedDone;
		},
		toggleSort() {
      	this.ascendingSort = !this.ascendingSort;
    	}
		},
		data() {
			return {
				ascendingSort: true
			}
		}
	};
</script>
