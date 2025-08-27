<template>
  <div class="min-h-screen flex flex-col items-center justify-center bg-gray-100 pb-20">
    <h1 class="text-3xl font-bold mb-6 text-blue-900">📊 Encuestas en Tiempo Real</h1>
    <!-- Componente Encuesta -->
     <Encuesta />
     <!-- Footer -->
      <Footer />
  </div>
</template>
<script setup>
import Encuesta from "./components/Survey.vue";
import Footer from "./components/Footer.vue";
</script>