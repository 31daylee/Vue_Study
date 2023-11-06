<script setup>
import { ref, onMounted } from 'vue'

/* Need to initialize with null value */
const pElementRef = ref(null)

onMounted(() => {
  pElementRef.value.textContent = 'Yeppi!'
})
</script>

<template>
  <p ref="pElementRef">hello</p>
</template>