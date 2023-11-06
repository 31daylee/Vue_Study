<script setup>
const emit = defineEmits(['response'])
emit('response', 'Hello from child')
</script>

<template>
  <h1>Child Component</h1>
</template>