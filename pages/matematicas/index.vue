<template>
  <div>
    <Navbar />
    <div class="container mx-auto mt-8">
      <h1 class="text-2xl font-bold">Matemáticas</h1>
      <ul class="mt-4 space-y-2">
        <li><a href="/matematicas/multiplicaciones" class="text-blue-500 hover:underline">Multiplicaciones</a></li>
        <li><a href="/matematicas/divisiones" class="text-blue-500 hover:underline">Divisiones</a></li>
        <li><a href="/matematicas/sumas" class="text-blue-500 hover:underline">Sumas</a></li>
        <li><a href="/matematicas/restas" class="text-blue-500 hover:underline">Restas</a></li>
      </ul>
    </div>
  </div>
</template>

<script setup>
import Navbar from '~/components/Navbar.vue';
</script>

<style scoped>
/* Add any additional styles if needed */
</style>
