<template>
  <h1>{{ title }}</h1>
  <input v-model="newEntry" type="text" name="" id="" /><button @click="addItem">Add</button>
  <ul>
    <li :key="index" v-for="(task, index) in tasks">
      {{ index + 1 + '-' + task }}
      <button @click="deleteItem(index)">X</button>
    </li>
  </ul>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  data() {
    return {
      newEntry: '',
      title: 'Todolist',
      tasks: ['Something to do', 'Other thing to do', 'Final thing to do'],
    }
  },
  methods: {
    addItem() {
      this.tasks.push(this.newEntry)
      this.newEntry = ''
    },
    deleteItem(index) {
      // Supprime l'élément correspondant dans la liste des tâches
      this.tasks.splice(index, 1)
    },
  },
})
</script>

<style scoped>
h1 {
  text-align: center;
  color: black;
  font-family: Cambria;
}
li {
  list-style: none;
}
</style>
