<template>
  <section id="SocialsComponent" class="py-24 px-4 text-white text-center">
    <h2 class="text-4xl md:text-6xl font-bold glitch-text mb-16">Join the Community</h2>

    <div class="flex flex-col md:flex-row justify-center items-center gap-6 max-w-2xl mx-auto mb-10">

      <!-- X -->
      <a
        href="https://x.com/wirebackwojak"
        target="_blank"
        rel="noopener noreferrer"
        class="glitch-button flex items-center justify-center gap-3 px-6 py-3 text-lg rounded w-56"
      >
        <img src="/icons/x.svg" alt="X" class="w-5 h-5" />
        Follow on X
      </a>

      <!-- Telegram -->
      <a
        href="https://t.me/wirebackcore"
        target="_blank"
        rel="noopener noreferrer"
        class="glitch-button flex items-center justify-center gap-3 px-6 py-3 text-lg rounded w-56"
      >
        <img src="/icons/telegram.svg" alt="Telegram" class="w-5 h-5" />
        Join Telegram
      </a>
    </div>

    <h2 class="text-4xl md:text-5xl font-bold mb-20 py-16">Be part of the robotic meta</h2>

  </section>
</template>



<script setup lang="ts">
</script>

<style scoped>
.bg-socials {
  background: radial-gradient(ellipse at center, #3a003f 10%, #000000 90%);
}


.glitch-text {
  position: relative;
  color: #0ff;
  text-shadow: 2px 0 red, -2px 0 blue;
  animation: glitch-flicker 2s infinite linear;
}

@keyframes glitch-flicker {
  0% { text-shadow: 2px 0 red, -2px 0 blue; }
  50% { text-shadow: -2px 0 red, 2px 0 blue; }
  100% { text-shadow: 2px 0 red, -2px 0 blue; }
}
</style>
