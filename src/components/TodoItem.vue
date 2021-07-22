<template>
  <li>
    <input v-if="task.done" type="checkbox" checked @change="onCheckChanged(task)"/>
    <input v-else type="checkbox" @change="onCheckChanged(task)"/>
    {{ task.label }}
  </li>
</template>

<script>
export default {
  name: 'TodoList',
  props: ['task', 'onCheckChanged'],
};
</script>