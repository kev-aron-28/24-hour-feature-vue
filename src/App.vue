<script setup lang="ts">
import { ref } from 'vue';
import StoriesBar from './components/StoryList.vue';
import StoryModal from './components/StoryModal.vue';

const isModalOpen = ref(false);

function openModal() {
  isModalOpen.value = true;
}

</script>

<template>
  <StoriesBar @open-modal="openModal"/>
  <StoryModal v-if="isModalOpen"/>
  
</template>

<style>
  body {
    position: relative;
  }
</style>
