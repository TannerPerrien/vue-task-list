<template>
  <div>
    <TodoList
      name="Monday"
      :tasks="tasksMonday" />
    <TodoList
      name="Tuesday"
      :tasks="tasksTuesday" />
    <TodoList
      name="Wednesday"
      :tasks="tasksWednesday" />
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
      tasksMonday: [{
        label: "Take out trash",
        done: false,
      }],
      tasksTuesday: [{
        label: "Chore #1",
        done: false,
      }, {
        label: "Chore #2",
        done: true,
      }, {
        label: "Chore #3",
        done: false,
      }],
      tasksWednesday: [{
        label: "Wednesday Task #1",
        done: false,
      }],
    }
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
