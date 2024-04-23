<template>
    <div>
      <h1>Lista de Tareas</h1>
      <input v-model="newTask" @keyup.enter="addTask" placeholder="Agregar nueva tarea">
      <ul>
        <li v-for="(task, index) in tasks" :key="index">
          <span>{{ task }}</span>
          <button @click="deleteTask(index)">Eliminar</button>
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        newTask: '',
        tasks: []
      };
    },
    methods: {
      addTask() {
        if (this.newTask.trim() !== '') {
          this.tasks.push(this.newTask.trim());
          this.newTask = '';
        }
      },
      deleteTask(index) {
        this.tasks.splice(index, 1);
      }
    }
  };
  </script>
  