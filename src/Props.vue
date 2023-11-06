<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue';
const greeting =ref('Hello!!')

</script>

<template>
  <ChildComp :msg="greeting"/>
</template>