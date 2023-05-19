<template>
	<li class="task__item" 
		:class="{ 'task__item--done' : done }">
		<span 
			class="task__item--text">
			{{ task.text }}
		</span>

		<div class="task__item--buttons">
			<delete-button
				@click="removeTask">
			</delete-button>
	
			<done-button 
				:done="done"
				@update:done="toggleDone">
			</done-button>
		</div>
	</li>
</template>

<script>
	import DeleteButton from './DeleteButton.vue';
	import DoneButton from './DoneButton.vue';

	export default {
	components: {
		DeleteButton,
		DoneButton
	},
	props: {
		task: {
			type: Object,
			required: true
		},
		done: {
			type: Boolean,
			required: true,
		},
	},
	methods: {
		removeTask() {
			this.$emit('task-removed', this.task);
		},
		toggleDone() {
			this.$emit('update:done', !this.done)
		}
	}
	};
</script>
 
<style>
	.task__item {
	display: flex;
	align-items: center;
	justify-content: space-between;
	margin: var(--margin-small);
	padding: 0.5rem;
	list-style: none;
	background-color: var(--color-light);
	}

	/* Style for tasks that is marked as Done */
  .task__item--done {
    text-decoration: line-through;
	 background: rgb(205, 61, 61);
    opacity: 0.6;
  }
 </style>