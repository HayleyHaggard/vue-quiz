<template>
  <div>
    <header class="header">
      <h1 class="header-title">Quizes</h1>
      <input
        class="header-input"
        v-model.trim="search"
        type="text"
        placeholder="Search..."
      />
    </header>
    <div class="cards-container">
      <My-card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />
    </div>
  </div>
</template>

<script setup>
import q from "../data/quizes.json";
import { ref, watch } from "vue";
import MyCard from "../components/My-card.vue";

const quizes = ref(q);
const search = ref("");

watch(search, () => {
  quizes.value = q.filter((quiz) =>
    quiz.name.toLowerCase().includes(search.value.toLowerCase())
  );
});
</script>

<style scoped>
.header {
  margin-bottom: 10px;
  margin-top: 30px;
  display: flex;
  align-items: center;
}

.header-title {
  margin-right: 30px;
  font-weight: bold;
}

.header-input {
  padding: 10px;
  width: 500px;
  background-color: rgba(128, 128, 128, 0.1);
  border-radius: 5px;
  border: none;
}

.cards-container {
  display: grid;
  grid-template-columns: repeat(auto-fill, 350px);
  justify-items: stretch;
  align-items: stretch;
  gap: 25px;
  margin-top: 40px;
}
</style>
