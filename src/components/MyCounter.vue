<script setup>
import { ref } from 'vue'
const counter = ref(0)
const incc = () => {
  counter.value++
}
</script>

<template>
  <div class="mmain">
    <p>{{ counter }}</p>
    <button @click="incc">+</button>
  </div>
</template>

<style>
.mmain {
  border: 1px;
}
</style>
