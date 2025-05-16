<script setup lang="ts">
import { ref } from 'vue'

const storyThumbs = ref<HTMLDivElement | null>(null)

const scrollLeft = () => {
  if (storyThumbs.value) {
    storyThumbs.value.scrollLeft -= 500
  }
}

const scrollRight = () => {
  if (storyThumbs.value) {
    storyThumbs.value.scrollLeft += 500
  }
}

const emit  = defineEmits<{
  openModal: []
}>()


function handleModal() {
  emit('openModal');
}

</script>

<template>
  <div class="story-header">
    <div class="story-header-arrow" @click="scrollLeft"></div>
    <div class="story-thumbs" ref="storyThumbs">
      <div class="story-circle" v-for="i in 15" :key="i" @click="handleModal" />
    </div>
    <div class="story-header-arrow" @click="scrollRight"></div>
  </div>
</template>

<style>
.story-header {
  display: flex;
  align-items: center;
  flex-direction: row;
  justify-content: space-between;
  box-sizing: border-box;
  width: 500px;
  height: 110px;
  background-color: red;
  overflow: hidden;
}

.story-header-arrow {
  width: 50px;
  height: 100%;
  background-color: aqua;
  cursor: pointer;
}

.story-thumbs {
  flex-grow: 1;
  overflow-x: auto;
  display: flex;
  gap: 10px;
  padding: 0 4px;
  scrollbar-width: none; /* Firefox */
}

.story-thumbs::-webkit-scrollbar {
  display: none; /* Chrome/Safari */
}

.story-circle {
  flex-shrink: 0; /* 👈 importante */
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background-color: blue;
  cursor: pointer;
}
</style>
