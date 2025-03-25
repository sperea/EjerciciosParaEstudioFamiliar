<template>
    <div class="flex items-center justify-center my-4">
      <div class="text-2xl font-bold pr-4">{{ dividend }}</div>
      <div class="border-l-4 border-b-4 border-gray-800 h-12 w-12 flex items-center justify-center">
        <div class="text-xl">{{ divisor }}</div>
      </div>
    <div class="mt-2">
      <!-- Removed quotient and remainder display -->
    </div>
  </div>
</template>

<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  dividend: Number,
  divisor: Number
});

// Calculate quotient and remainder
const quotient = Math.floor(props.dividend / props.divisor);
const remainder = props.dividend % props.divisor;
</script>

<style scoped>
/* Add any additional styles if needed */
</style>
