<script setup>
import { ref, computed } from 'vue';
import Content from './components/Content.vue';

const noError = ref(false);
const fetchedData = ref({});

fetch('/data.json')
    .then(response => response.json())
    .then(data => {
      console.log(data);
      fetchedData.value = data;
      noError.value = true;
    })
    .catch(error => console.error("Could not load JSON data:", error));

const dataObj = computed(() => fetchedData.value);
</script>

<template>
  <Content v-if="noError" :data="dataObj" />
  <div v-else>Error. no data.</div>
</template>

<style scoped>
</style>
