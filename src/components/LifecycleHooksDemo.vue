<template>
  <div>
    <h2>Lifecycle Hooks Demo</h2>
    <p>{{ message }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'

const message = ref('The component is not yet mounted.')

onMounted(() => {
  message.value = 'The component is now mounted. 🗿'
})
</script>