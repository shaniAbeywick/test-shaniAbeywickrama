<template>
  <div class="flex items-center justify-center h-screen">
    <button @click="showModal = true" class="bg-blue-600 text-white px-4 py-2 rounded-md hover:bg-blue-700">Click Me</button>
    <DialogWindow :isVisible="showModal" @close="showModal = false" @deactivate="handleDeactivation"></DialogWindow>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import DialogWindow from './components/DialogWindow.vue';

const showModal = ref(false);

function handleDeactivation() {
  
  console.log('Account deactivated');
  showModal.value = false;
}
</script>

<style scoped>

</style>



