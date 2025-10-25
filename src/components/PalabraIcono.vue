<template>
  <div @click="playAudio"
       class="flex flex-col items-center border border-gray-300 rounded-xl p-3 w-28 m-2 cursor-pointer transform transition-transform hover:scale-105">
    <div class="text-4xl">{{ icono }}</div>
    <div class="text-center mt-1">
      <h3 class="font-semibold">{{ nahuatl }}</h3>
      <p class="text-sm text-gray-600">{{ espanol }}</p>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'

defineProps({
  icono: String,
  nahuatl: String,
  espanol: String,
  audio_url: String
})

const audio = ref(null)
const playAudio = () => {
  audio.value = new Audio(audio_url)
  audio.value.play()
}
</script>

<!-- No style aquí, todo Tailwind -->
