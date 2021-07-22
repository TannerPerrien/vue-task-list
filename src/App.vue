<template>
  <div>
    <TodoList
      name="Monday"
      :tasks="tasksForDay(1)"
      :onCheckChanged="onCheckChanged" />
    <TodoList
      name="Tuesday"
      :tasks="tasksForDay(2)"
      :onCheckChanged="onCheckChanged" />
    <TodoList
      name="Wednesday"
      :tasks="tasksForDay(3)"
      :onCheckChanged="onCheckChanged" />
  </div>
</template>

<script>
import TodoList from './components/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList
  },
  data: function() {
    return  {
      tasks: [{
        id: 1,
        day: 1,
        label: "Take out trash",
        done: false,
      }, {
        id: 2,
        day: 2,
        label: "Chore #1",
        done: false,
      }, {
        id: 3,
        day: 2,
        label: "Chore #2",
        done: true,
      }, {
        id: 4,
        day: 2,
        label: "Chore #3",
        done: false,
      }, {
        id: 5,
        day: 3,
        label: "Wednesday Task #1",
        done: false,
      }]
    }
  },

  methods: {
    tasksForDay(dayId) {
      return this.tasks.filter(task => task.day === dayId);
    },
    onCheckChanged(task) {
      const internalTask = this.tasks.find(t => t.id === task.id);
      internalTask.done = !internalTask.done;
    },
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
