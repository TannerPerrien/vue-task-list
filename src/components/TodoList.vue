<template>
    <div>
      <h2>{{ name }}</h2>
      <button @click="markAllDone">Mark all done</button>
      <button @click="markAllUndone">Mark all undone</button>
      <ol>
        <TodoItem v-for="task in tasks"
          :task="task"
          :onCheckChanged="onCheckChanged"
        />
      </ol>
    </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
  name: 'TodoList',
  components: {
    TodoItem,
  },

  props: ['name', 'tasks', 'onCheckChanged'],
  
  methods: {
    markAllDone() {
      this.markTasks(true);
    },
    markAllUndone() {
      this.markTasks(false);
    },
    markTasks(done) {
      this.tasks.forEach(task => {
        task.done = done;
      })
    },
  },
};
</script>
