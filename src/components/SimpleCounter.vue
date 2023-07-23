<script setup>
import { ref } from 'vue'
const count = ref(0)
</script>

<template>
  <div class="card">
    <div class="card-body">
      <button class="btn btn-primary" type="button" @click="count++">count is {{ count }}</button>
    </div>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
