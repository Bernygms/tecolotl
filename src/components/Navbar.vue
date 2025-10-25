<template>
  <nav class="flex items-center gap-2 p-2 bg-gray-200">
    <img :src="logo" alt="Logo de la página" class="h-10" />
    <span class="font-bold text-lg">Tecolotl</span>
  </nav>
</template>

<script>
import logo from '../assets/logo.png'

export default {
  name: 'Navbar',
  data() {
    return { logo }
  }
}
</script>

<!-- No es necesario <style> si usas Tailwind -->
