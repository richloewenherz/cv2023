<script setup>
import {ref} from 'vue'

defineProps({
  data: Object
})

const count = ref(0)
</script>

<template>
  <h1>{{ data.title }}</h1>

  <h2>{{ data.subtitle }}</h2>

  <p>{{ data.text }}</p>

  <div class="card">
    <button type="button" @click="count++">count is {{ count }}</button>
  </div>

</template>

<style scoped>
</style>
