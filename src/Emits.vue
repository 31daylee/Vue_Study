<script setup>
import { ref } from 'vue'
import ChildComp from './ChildComp.vue'
const childMsg =ref('Not yet')

</script>

<template>
  <ChildComp @response="(msg) => childMsg == msg"/>
  <p>{{childMsg}}</p>
</template>