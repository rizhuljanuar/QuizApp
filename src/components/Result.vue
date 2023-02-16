<script setup>
  import { defineProps } from 'vue'
  import { RouterLink } from 'vue-router'

  const {numberOfCurrentAnswer, quizQuestionLength} = defineProps(["numberOfCurrentAnswer", "quizQuestionLength"])
</script>

<template>
  <div class="result">
    <p>Your Results...</p>
    <Transition name="nilai" appear>
      <h1>
        {{ numberOfCurrentAnswer }} / {{ quizQuestionLength }}
      </h1>
    </Transition>
    <RouterLink to="/">Go back</RouterLink>
  </div>
</template>

<style scoped>
  .result {
    text-align: center;
    padding: 100px 0;
  }

  p {
    font-size: 25px;
  }

  h1 {
    font-size: 80px;
  }

  .nilai-enter-from {
    opacity: 0;
    transform: translateY(-60px);
  }

  .nilai-enter-to {
    opacity: 1;
    transform: translateY(0);
  }

  .nilai-enter-active {
    transition: all 1s ease;
  }
</style>
