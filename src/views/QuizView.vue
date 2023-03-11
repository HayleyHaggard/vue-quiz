<template>
  <div>
    <MyQuizheader
      :barPercentage="barPercentage"
      :questionStatus="questionStatus"
    />
    <div>
      <MyQuestion
        v-if="!showResults"
        :question="quiz.questions[currentQuestionIndex]"
        @selectOption="onOptionSelected"
      />
      <MyResult
        v-else
        :quizQuestionsLength="quiz.questions.length"
        :numberOfCorrectAnswers="numberOfCorrectAnswers"
      />
    </div>
  </div>
</template>

<script setup>
import MyQuestion from "../components/My-question.vue";
import MyQuizheader from "../components/My-quizheader.vue";
import MyResult from "../components/My-result.vue";
import quizes from "../data/quizes.json";

import { useRoute } from "vue-router";
import { ref, computed } from "vue";

const route = useRoute();
const quizId = parseInt(route.params.id);

const quiz = quizes.find((q) => q.id === quizId);

const currentQuestionIndex = ref(0);
const numberOfCorrectAnswers = ref(0);
const showResults = ref(false);

const questionStatus = computed(() => {
  return `${currentQuestionIndex.value}/${quiz.questions.length}`;
});

const barPercentage = computed(
  () => `${(currentQuestionIndex.value / quiz.questions.length) * 100}%`
);

const onOptionSelected = (isCorrect) => {
  if (isCorrect) {
    numberOfCorrectAnswers.value++;
  }

  if (quiz.questions.length - 1 === currentQuestionIndex.value) {
    showResults.value = true;
  }

  currentQuestionIndex.value++;
};
</script>

<style scoped></style>
