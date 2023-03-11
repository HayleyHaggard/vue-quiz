<template>
  <div class="card" @click="navigateToQuiz">
    <img class="card-img" :src="quiz.img" alt="" />
    <div class="card-text">
      <h2 class="card-title">{{ quiz.name }}</h2>
      <p class="card-questions">{{ quiz.questions.length }} questions</p>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from "vue";
import { useRouter } from "vue-router";

const router = useRouter();
// eslint-disable-next-line vue/no-setup-props-destructure
const { quiz } = defineProps(["quiz"]);

const navigateToQuiz = () => {
  router.push(`/quiz/${quiz.id}`);
};
</script>

<style scoped>
.card {
  border-radius: 2%;
  box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.2);
  overflow: hidden;
  cursor: pointer;
}

.card-img {
  margin: 0;
  height: 190px;
  width: 100%;
}

.card-text {
  padding: 15px;
}

.card-title {
  font-weight: bold;
}
</style>
