<script setup>
import { ref } from "vue";
import ChildComp from "./ChildComp2.vue";

const msg = ref("Show me the message!");
</script>

<template>
  <ChildComp>msg : {{ msg }}</ChildComp>
</template>
