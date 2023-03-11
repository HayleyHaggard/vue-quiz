<template>
  <header>
    <h4 class="header-title">Question {{ questionStatus }}</h4>
    <div class="header-bar">
      <div class="header-completion" :style="{ width: barPercentage }"></div>
    </div>
  </header>
</template>

<script setup>
import { defineProps } from "vue";

// eslint-disable-next-line vue/no-setup-props-destructure
const { questionStatus, barPercentage } = defineProps([
  "questionStatus",
  "barPercentage",
]);
</script>

<style scoped>
header {
  margin-top: 20px;
}

.header-title {
  margin-bottom: 20px;
  font-size: 30px;
}

.header-bar {
  width: 100%;
  height: 10px;
  border: 3px solid rgb(207, 141, 255);
}

.header-completion {
  height: 100%;
  width: 0%;
  background-color: rgb(207, 141, 255);
}
</style>
