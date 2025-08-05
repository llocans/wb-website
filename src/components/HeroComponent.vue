<template>
  <section class="min-h-screen bg-black text-white flex flex-col justify-center items-center text-center px-4">
    <img :src="logo" alt="Wireback Logo" class="w-36 md:w-56 object-contain mb-6 drop-shadow-lg" />
    
    <h1 class="text-4xl md:text-6xl font-bold tracking-wide glitch">$WIREBACK</h1>
    
    <p class="mt-4 text-lg md:text-xl text-gray-300 max-w-md">
      The autonomous memecoin born from the machine.
    </p>
  </section>
</template>

<script setup lang="ts">
import logo from '@/assets/img/pfp.png'
</script>

<style scoped>
.glitch {
  position: relative;
  color: #0ff;
  text-shadow: 1px 0 red, -1px 0 blue;
  animation: glitch 2s infinite;
}

@keyframes glitch {
  0% {
    text-shadow: 1px 0 red, -1px 0 blue;
  }
  20% {
    text-shadow: -2px 2px red, 2px -2px blue;
  }
  40% {
    text-shadow: 1px -1px red, -1px 1px blue;
  }
  60% {
    text-shadow: -1px -1px red, 1px 1px blue;
  }
  80% {
    text-shadow: 0px 0px red, 0px 0px blue;
  }
  100% {
    text-shadow: 1px 0 red, -1px 0 blue;
  }
}
</style>
