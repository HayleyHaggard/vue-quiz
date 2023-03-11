<template>
  <div class="results">
    <p class="results-text">Your results...</p>
    <h1 class="results-title">{{ finalResults }}</h1>
    <router-link class="results-link" :to="{ name: 'quizes' }"
      >Go back</router-link
    >
  </div>
</template>

<script setup>
import { defineProps, computed } from "vue";
import { RouterLink } from "vue-router";

// eslint-disable-next-line vue/no-setup-props-destructure
const { quizQuestionsLength, numberOfCorrectAnswers } = defineProps([
  "quizQuestionsLength",
  "numberOfCorrectAnswers",
]);

const finalResults = computed(() => {
  return `${numberOfCorrectAnswers}/${quizQuestionsLength}`;
});
</script>

<style scoped>
.results {
  text-align: center;
  padding: 100px 0;
}

.results-text {
  font-size: 25px;
}

.results-title {
  margin-bottom: 40px;
  font-size: 90px;
}

.results-link {
  padding: 20px;
  font-size: 25px;
  border-radius: 5px;
  color: black;
  background-color: rgb(244, 239, 239);
}
</style>
