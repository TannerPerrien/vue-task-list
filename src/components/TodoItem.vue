<template>
  <li>
    <input v-if="task.done" type="checkbox" checked/>
    <input v-else type="checkbox" />
    {{ task.label }}
  </li>
</template>

<script>
export default {
  name: 'TodoList',
  props: ['task'],
};
</script>