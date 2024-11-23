<template>
  <h1>{{ title }}</h1>
  <ul>
    <li :key="task.index" v-for="task in tasks">
      {{ task }}
      <button>X</button>
    </li>
  </ul>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      title: 'Todolist',
      tasks: ['Something to do', 'Other thing to do', 'Final thing to do'],
    }
  },
})
</script>

<style scoped>
h1 {
  text-align: center;
  color: black;
  font-family: Cambria;
}
</style>
