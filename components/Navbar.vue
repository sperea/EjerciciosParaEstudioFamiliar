<template>
  <nav class="bg-gradient-to-r from-blue-500 to-purple-600 p-4 shadow-lg">
    <div class="container mx-auto flex justify-between items-center">
      <NuxtLink to="/" class="text-white text-2xl font-extrabold">Inicio</NuxtLink>

      <!-- Menú Matemáticas -->
      <div class="relative group pt-6">  <!-- Added padding-top -->
        <button class="text-white text-lg hover:text-yellow-300 transition duration-300 focus:outline-none">
          Matemáticas
        </button>
        <div class="absolute hidden group-hover:block bg-white text-gray-800 mt-2 rounded shadow-lg top-full">  <!-- Added top-full -->
          <NuxtLink to="/matematicas/multiplicaciones" class="block px-4 py-2 hover:bg-gray-200">Multiplicaciones</NuxtLink>
          <NuxtLink to="/matematicas/divisiones" class="block px-4 py-2 hover:bg-gray-200">Divisiones</NuxtLink>
          <NuxtLink to="/matematicas/sumas" class="block px-4 py-2 hover:bg-gray-200">Sumas</NuxtLink>
          <NuxtLink to="/matematicas/restas" class="block px-4 py-2 hover:bg-gray-200">Restas</NuxtLink>
        </div>
      </div>

      <!-- Menú Soluciones -->
      <div class="relative group pt-6">  <!-- Added padding-top -->
        <button class="text-white text-lg hover:text-yellow-300 transition duration-300 focus:outline-none">
          Solucionar
        </button>
        <div class="absolute hidden group-hover:block bg-white text-gray-800 mt-2 rounded shadow-lg top-full">  <!-- Added top-full -->
          <NuxtLink to="/soluciones/solucionar-division" class="block px-4 py-2 hover:bg-gray-200">Divisiones</NuxtLink>
        </div>
      </div>
    </div>
  </nav>
</template>

<style scoped>
/* Mejorar la interacción del menú desplegable */
.relative.group:hover .absolute {
  display: block;
}

/* Crear un área de hover más grande */
.group .absolute {
  margin-top: 0.5rem; /* Ajusta según necesites */
}

.group:hover .absolute {
  display: block;
}

/* Asegurar transición suave */
.absolute {
  transition: all 0.3s ease;
  min-width: 200px;
}
</style>