<template>
  <div class="container mx-auto">
    <h1 class="text-2xl font-bold mb-4 mt-20">Aprendamos a Dividir Paso a Paso</h1>
    <form @submit.prevent="resolverDivision">
      <div class="mb-4">
        <label class="block text-sm font-medium">Número a dividir (dividendo):</label>
        <input type="number" v-model.number="dividendo" required class="input" />
      </div>
      <div class="mb-4">
        <label class="block text-sm font-medium">Número por el que divides (divisor):</label>
        <input type="number" v-model.number="divisor" required class="input" />
      </div>
      <button type="submit" class="btn">Calcular y explicar</button>
    </form>

    <div v-if="resultado" class="mt-6">
      <h2 class="text-xl font-semibold">Resultado:</h2>
      <p>{{ resultado }}</p>
      <h3 class="text-lg font-medium">Cómo lo resolvemos paso a paso:</h3>
      <ul class="list-disc pl-5">
        <li v-for="(paso, index) in pasos" :key="index">{{ paso }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dividendo: null,
      divisor: null,
      resultado: null,
      pasos: [],
    };
  },
  methods: {
    resolverDivision() {
      this.pasos = [];
      if (this.divisor === 0) {
        this.resultado = "No se puede dividir por cero.";
        return;
      }

      const dividendoStr = String(this.dividendo);
      let resto = 0;
      let cocienteStr = "";

      for (let i = 0; i < dividendoStr.length; i++) {
        const cifraActual = Number(dividendoStr[i]);
        resto = resto * 10 + cifraActual;
        this.pasos.push(`Tomamos la cifra ${cifraActual} y la añadimos al resto anterior, obteniendo ${resto}.`);

        if (resto < this.divisor) {
          cocienteStr += cocienteStr ? "0" : "";
          this.pasos.push(`Como ${resto} es menor que ${this.divisor}, colocamos un 0 en el cociente y continuamos.`);
        } else {
          const cocienteParcial = Math.floor(resto / this.divisor);
          cocienteStr += cocienteParcial;
          this.pasos.push(`¿Cuántas veces cabe ${this.divisor} en ${resto}? Cabe ${cocienteParcial} veces.`);
          const multiplicacion = cocienteParcial * this.divisor;
          this.pasos.push(`Multiplicamos ${cocienteParcial} por ${this.divisor}, obteniendo ${multiplicacion}.`);
          resto -= multiplicacion;
          this.pasos.push(`Restamos ${multiplicacion} de ${resto + multiplicacion} y obtenemos un nuevo resto de ${resto}.`);
        }
      }

      this.resultado = `El cociente es ${cocienteStr} y el resto final es ${resto}.`;
    }
  }
};
</script>

<style scoped>
.container {
  max-width: 600px;
  margin: auto;
  font-family: Arial, sans-serif;
}
.input {
  width: 100%;
  padding: 8px;
  border: 1px solid #ccc;
  border-radius: 4px;
}
.btn {
  background-color: #4caf50;
  color: white;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
}
</style>