<template>
  <Navbar />

  <div class="flex justify-center items-center h-screen bg-blue-100">
    <h1 class="text-3xl font-bold text-blue-800">¡Hola Tailwind!</h1>
  </div>

  <!-- Grilla de palabras -->
  <div class="flex flex-wrap justify-center">
    <PalabraIcono
      v-for="palabra in palabras"
      :key="palabra.nahuatl"
      :icono="palabra.icono"
      :nahuatl="palabra.nahuatl"
      :espanol="palabra.espanol"
      :audio_url="palabra.audio_url"
    />
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import PalabraIcono from './components/PalabraIcono.vue'
import Navbar from './components/Navbar.vue'

const palabras = ref([])

onMounted(async () => {
  const res = await fetch('/src/data/naturaleza.json')
  palabras.value = await res.json()
})
</script>

<!-- No es necesario <style> -->
