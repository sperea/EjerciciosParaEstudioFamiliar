<template>
  <div class="container mx-auto mt-8">
    <h1 class="text-2xl font-bold mb-4">Divisiones</h1>
    <form @submit.prevent="generateExercises" class="mb-8">
      <div class="flex space-x-4">
        <div>
          <label for="dividendDigits" class="block text-sm font-medium text-gray-700">Cifras del Dividendo</label>
          <input type="number" id="dividendDigits" v-model="dividendDigits" min="1" class="mt-1 block w-full border-gray-300 rounded-md shadow-sm" required>
        </div>
        <div>
          <label for="divisorDigits" class="block text-sm font-medium text-gray-700">Cifras del Divisor</label>
          <input type="number" id="divisorDigits" v-model="divisorDigits" min="1" class="mt-1 block w-full border-gray-300 rounded-md shadow-sm" required>
        </div>
        <div>
          <label for="exerciseCount" class="block text-sm font-medium text-gray-700">Número de Ejercicios</label>
          <input type="number" id="exerciseCount" v-model="exerciseCount" min="1" class="mt-1 block w-full border-gray-300 rounded-md shadow-sm" required>
        </div>
      </div>
      <button type="submit" class="mt-4 bg-blue-500 text-white px-4 py-2 rounded-md shadow hover:bg-blue-600">Generar Ejercicios</button>
    </form>
    <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8">
      <div v-for="(exercise, index) in exercises" :key="index">
        <Division :dividend="exercise.dividend" :divisor="exercise.divisor" />
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import Navbar from '~/components/Navbar.vue';
import Division from '~/components/Division.vue';

const dividendDigits = ref(1);
const divisorDigits = ref(1);
const exerciseCount = ref(1);
const exercises = ref([]);

const generateExercises = () => {
  exercises.value = [];
  for (let i = 0; i < exerciseCount.value; i++) {
    const dividend = Math.floor(Math.random() * (10 ** dividendDigits.value));
    const divisor = Math.floor(Math.random() * (10 ** divisorDigits.value) + 1); // Avoid zero divisor
    exercises.value.push({ dividend, divisor });
  }
};
</script>

<style scoped>
/* Add any additional styles if needed */
</style>
