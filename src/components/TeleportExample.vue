<script setup lang="ts">
import { type Ref, ref } from 'vue';
import ModalBasic from './ModalBasic.vue';

const show: Ref<boolean> = ref(false);
const showTwo: Ref<boolean> = ref(false);

const showModal = () => {
  show.value = !show.value;
};
const showModaltwo = () => {
  showTwo.value = !showTwo.value;
};
</script>

<template>
  <button @click="showModal">Open 1</button>
  <button @click="showModaltwo">Open 2</button>

  <Teleport to="body">
    <ModalBasic :show="show" @close="showModal" title="soy modal 1" />
  </Teleport>

  <Teleport to="body">
    <ModalBasic :show="showTwo" @close="showModaltwo" title="soy modal 2" />
  </Teleport>
</template>

<style scoped></style>
