<script setup lang="ts">
import pfp from '../assets/img/pfp.png'
</script>

<template>
  <section class="min-h-screen bg-black text-white flex flex-col justify-center items-center text-center px-4">
    <h1 class="text-5xl font-bold mb-4 tracking-wider">$WIREBACK</h1>
    <img :src="pfp" alt="Wireback Meme" class="w-48 h-48 object-contain mt-4 rounded-full border border-gray-700 shadow-lg" />
    <p class="text-gray-400 text-sm mt-4">The robotic meta leader...</p>
  </section>
</template>
