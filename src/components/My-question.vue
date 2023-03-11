<template>
  <div class="question-container">
    <h1 class="question-text">{{ question.text }}</h1>
  </div>
  <div class="option-container">
    <div
      v-for="option in question.options"
      :key="option.id"
      @click="emitSelectedOption(option.isCorrect)"
      class="option-box"
    >
      <p class="option-label">{{ option.label }}</p>
      <div class="option-value">
        <p>{{ option.text }}</p>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps, defineEmits } from "vue";

// eslint-disable-next-line vue/no-setup-props-destructure
const { question } = defineProps(["question"]);

const emit = defineEmits(["selectOption"]);

const emitSelectedOption = (isCorrect) => {
  emit("selectOption", isCorrect);
};
</script>

<style scoped>
.question-container {
  margin-top: 20px;
}

.question-text {
  margin-bottom: 20px;
  font-size: 40px;
}

.option-box {
  display: flex;
  margin-bottom: 20px;
  cursor: pointer;
}

.option-label {
  display: flex;
  justify-content: center;
  align-items: center;
  width: 50px;
  height: 50px;
  background-color: rgb(207, 141, 255);
  font-size: 30px;
}

.option-value {
  background-color: rgb(244, 239, 239);
  width: 100%;
  font-size: 30px;
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
</style>
