<script setup>
import {ref} from 'vue'

// give each todo a unique id
let id = 0

// reset 
const newTodo = ref('')
const todos = ref([
  { id: id++, text: 'Learn HTML' },
  { id: id++, text: 'Learn Vue' }
])

// insert the value & reset '' 
function addTodo(){
  todos.value.push({id: id++, text: newTodo.value})
  newTodo.value = ''
}

// if click the button for remoteTodo 
function removeTodo(todo){
  todos.value = todos.value.filter((t) => t !== todo)
}


</script>
<template>
  <form @submit.prevent="addTodo">
    <input v-model="newTodo"> /*v-model: v-bind + v-on */
    <button>Add Todo</button>
  </form>
  <ul>
    <li v-for="todo in todos" :key="todo.id">
      {{todo.text}}
      <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
</template>
