<template>
	<li class="task__item">
		<!-- Span styling marks Done/Not Done -->
		<span 
			class="task__item--text"
			:class="{ done: task.done }">{{ task.text }}
		</span>

		<div class="task__item--buttons">
			<delete-button
				@click="removeTask">
			</delete-button>
	
			<done-button 
				:done="task.done"
				@click="toggleDone">
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
		}
	},
	methods: {
		removeTask() {
			this.$emit('task-removed', this.task);
		},
		toggleDone() {
			this.$emit('toggle-done');
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

	.done {
	text-decoration: line-through;
	color: gray;
	}
 </style>