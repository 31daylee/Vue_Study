<script setup>
import {ref , computed} from 'vue'

let id = 0

// reset 
const newTodo = ref('')
const hideCompleted = ref(false)
const todos = ref([
  { id: id++, text: 'Learn HTML', done:true},
  { id: id++, text: 'Learn Vue' , done:false}
])

const filteredTodos = computed(()=>{
    return hideCompleted.value ? todos.value.filter((t)=> !t.done) : todos.value

})

// insert the value & reset '' 
function addTodo(){
  todos.value.push({id: id++, text: newTodo.value, done:false})
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
        <input type="checkbox" v-model="todo.done">
        <span :class="{done : todo.done}">{{todo.done}}</span>
        <button @click="removeTodo(todo)">X</button>
    </li>
  </ul>
  <button @click="hideCompleted = !hideCompleted">
    {{hideCompleted ? 'show' : 'hideCompleted'}}
  </button>
</template>
<style>
.done{
    text-decoration: line-through;
}
</style>


