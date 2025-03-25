<template>
  <div class="flex items-center justify-center my-4">
    <div class="text-2xl font-bold  pr-4">{{ dividend }}</div>
    <div class="flex flex-col items-center">

      <div class="border-l-4 border-b-4 border-gray-800 h-12 w-12 flex items-center justify-center">
        <div class="text-xl ">{{ divisor }}</div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  dividend: Number,
  divisor: Number
});
</script>

<style scoped>
/* Add any additional styles if needed */
</style>
