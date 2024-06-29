<script setup lang="ts">
import { type Ref } from 'vue';
defineProps<{
  show: Ref<boolean>;
  title: string;
}>();
</script>

<template>
  <div v-if="show" class="dialog">
    <div class="modal">
      <h2>{{ title }}</h2>
      <button @click="$emit('close')">Close</button>
    </div>
  </div>
</template>

<style scoped>
.dialog {
  position: fixed;
  display: flex;
  justify-content: center;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background: rgba(0, 0, 0, 0.8);
  z-index: 99999;
}

.modal {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  width: 400px;
  height: 400px;
  background: rgba(80, 80, 80, 0.8);
}
</style>
