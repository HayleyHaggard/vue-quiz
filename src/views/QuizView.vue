<template>
  <div>
    <MyQuizheader />
    <div>
      <MyQuestion :question="quiz.questions[currentQuestionIndex]" />
    </div>
  </div>
</template>

<script setup>
import MyQuestion from "../components/My-question.vue";
import MyQuizheader from "../components/My-quizheader.vue";
import quizes from "../data/quizes.json";

import { useRoute } from "vue-router";
import { ref } from "vue";

const route = useRoute();

const quizId = parseInt(route.params.id);

const quiz = quizes.find((q) => q.id === quizId);

const currentQuestionIndex = ref(0);
</script>

<style scoped></style>
