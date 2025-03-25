<template>
  <nav class="bg-gradient-to-r from-blue-500 to-purple-600 p-4 shadow-lg">
    <div class="container mx-auto flex justify-between items-center">
      <a href="/" class="text-white text-2xl font-extrabold">Inicio</a>
      <div class="relative group">
        <button class="text-white text-lg hover:text-yellow-300 transition duration-300 focus:outline-none">
          Matemáticas
        </button>
        <div class="absolute hidden group-hover:block bg-white text-gray-800 mt-2 rounded shadow-lg">
          <a href="/matematicas/multiplicaciones" class="block px-4 py-2 hover:bg-gray-200">Multiplicaciones</a>
          <a href="/matematicas/divisiones" class="block px-4 py-2 hover:bg-gray-200">Divisiones</a>
          <a href="/matematicas/sumas" class="block px-4 py-2 hover:bg-gray-200">Sumas</a>
          <a href="/matematicas/restas" class="block px-4 py-2 hover:bg-gray-200">Restas</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup>
// No script logic needed for static navbar
</script>

<style scoped>
/* Add any additional styles if needed */
</style>
