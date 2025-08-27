<template>
  <div class="bg-white shadow-lg rounded-2xl p-6 w-96">
    <h2 class="text-xl font-semibold mb-4 text-blue-900">📊 Encuestas</h2>

    <!-- Selección de categoría -->
    <div class="mb-4">
      <label class="font-semibold text-blue-600">Selecciona categoría:</label>
      <select v-model="categoriaSeleccionada" class="w-full mt-2 p-2 border rounded-lg text-blue-600 bg-blue-200 font-semibold">
        <option class="font-semibold" v-for="(opciones, categoria) in encuestas" :key="categoria" :value="categoria">
          {{ categoria }}
        </option>
      </select>
    </div>

    <!-- Opciones de la encuesta -->
    <div class="space-y-2">
      <button 
        v-for="opcion in encuestas[categoriaSeleccionada]" 
        :key="opcion" 
        @click="votar(opcion)"
        class="w-full py-2 px-4 bg-blue-500 text-white font-semibold rounded-lg hover:bg-blue-600"
      >
        {{ opcion }}
      </button>
    </div>

    <!-- Resultados -->
    <div class="mt-6">
      <h3 class="font-bold text-blue-600">Resultados:</h3>
      <ul>
        <li class="font-semibold text-blue-800" v-for="(votos, opcion) in resultados[categoriaSeleccionada]" :key="opcion">
          {{ opcion }}: {{ votos }} votos
        </li>
      </ul>
    </div>

    <!-- Botón de reinicio -->
    <div class="mt-6 flex justify-center">
      <button @click="reiniciarEncuesta" class="px-4 py-2 bg-red-500 text-white font-semibold rounded-lg hover:bg-red-800">
        Reiniciar Encuesta
      </button>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

// Categorías de encuestas con sus opciones
const encuestas = {
  "Lenguajes de Programación": ["JavaScript", "Python", "Java", "C#"],
  "Frameworks Frontend": ["Vue", "React", "Angular", "Svelte"],
  "Bases de Datos": ["MySQL", "PostgreSQL", "MongoDB", "SQLite"],
};

// Resultados iniciales (todos en 0)
const resultados = ref({});
for (const categoria in encuestas) {
  resultados.value[categoria] = {};
  encuestas[categoria].forEach(opcion => {
    resultados.value[categoria][opcion] = 0;
  });
}

// Categoría seleccionada (por defecto la primera)
const categoriaSeleccionada = ref(Object.keys(encuestas)[0]);

// Función para votar
function votar(opcion) {
  resultados.value[categoriaSeleccionada.value][opcion]++;
}

// Reiniciar votos de la categoría actual
function reiniciarEncuesta() {
  encuestas[categoriaSeleccionada.value].forEach(opcion => {
    resultados.value[categoriaSeleccionada.value][opcion] = 0;
  });
}
</script>
