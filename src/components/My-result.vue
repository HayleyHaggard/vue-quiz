<template>
  <div class="results">
    <p></p>
    <h1>{{ finalResults }}</h1>
    <router-link :to="{ name: 'quizes' }">Go Back</router-link>
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
p {
  font-size: 25px;
}

h1 {
  font-size: 90px;
}
</style>
