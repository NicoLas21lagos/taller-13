<template>
    <div>
      <h1>Lista de Tareas</h1>
      <input id="id" v-model="newTask" @keyup.enter="addTask" placeholder="Agregar nueva tarea">
      <div id="container">
      <ul>
        <li v-for="(task, index) in tasks" :key="index">
          <span>{{ task }}</span>
          <button id="btn" @click="deleteTask(index)"> Eliminar</button>
          <button id="btn">Renombrar</button>
        </li>
      </ul>
      </div>
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

  <style>
  h1{
    text-align: center
  }

  #id{
    position: relative;
    text-align: center;
    left: 1rem;
  }

  #container{
    position: relative;
    left: 10rem;
  }

  #btn{
    border-radius: 10px;
    margin: 10px;
  }
  </style>
  