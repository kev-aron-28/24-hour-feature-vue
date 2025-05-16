<script lang="ts">
function modalTimer() {

}
</script>

<template>
  <div class="story-modal">
    <div class="story-modal-content">
      <div class="story-modal-progress">
        <div class="story-modal-progress-line"></div>
      </div>
      <div class="story-modal-media"></div>
    </div>
</div>
</template>

<style>
  .story-modal {
    width: 100vw;
    height: 100vh;
    background-color: #00000094;
    position: absolute;
    top: 0;
    left: 0;
    display: flex;
    align-items: center;
    justify-content: center;
  }

    .story-modal-content {
      width: 400px;
      height: 90%;
      background-color: red;
      border-radius: 4px;
    }

    .story-modal-progress {
      width: 95%;
      height: 3px;
      background-color: rgb(187, 187, 187);
    }

    .story-modal-progress-line {
    }

</style>
