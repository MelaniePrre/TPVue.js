<template>
  <div id="app">
    <ul>
      <li v-for="(task, index) in tasks" :key="index">{{ task }}</li>
    </ul>

    <div>
      <h3 v-if="coloreTitre" :style="{color: 'blue'}">Listing</h3>
      <input v-model="newTask" placeholder="Nouvelle tâche" />
      <button @click="addTask">Ajouter</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",

  data() {
    return {
      tasks: [],
      newTask: "",
      coloreTitre: true,
    };
  },

  methods: {
    addTask: function () {
      if (this.newTask !== "") {
        this.tasks.push(this.newTask);
        this.newTask = "";
      }
    },
  },
};
</script>

<style></style>
