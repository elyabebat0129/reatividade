<script setup>
import { ref, onMounted, onUpdated, onUnmounted } from 'vue'

const emit = defineEmits(['log'])

const clicks = ref(0)

onMounted(() => emit('log', 'onMounted'))
onUpdated(() => emit('log', 'onUpdated'))
onUnmounted(() => emit('log', 'onUnmounted'))
</script>

<template>
  <div class="border rounded p-3">
        <p class="mb-1">Clicks: <strong class="text-success">{{ clicks }}</strong></p>
        <button class="btn btn-success btn-sm" @click="clicks++">Click here</button>
        <p class="text-muted small mt-2 mb-0">Click to trigger onUpdated</p>
  </div>
</template>

<style scoped>
.border {
  border-color: #198754 !important;
}
</style>