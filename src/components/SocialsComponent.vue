<template>
  <section class="py-16 px-4 bg-socials text-white text-center">
    <h2 class="text-4xl md:text-5xl font-bold glitch-text mb-10">Join the Community</h2>

    <div class="grid gap-6 md:grid-cols-2 max-w-2xl mx-auto">
      <!-- X -->
      <a
        href="https://x.com/wirebackwojak"
        target="_blank"
        rel="noopener noreferrer"
        class="glitch-button flex items-center justify-center gap-3 px-6 py-3 text-lg rounded"
      >
        <img src="/icons/x.svg" alt="X" class="w-5 h-5" />
        Follow on X
      </a>

      <!-- Telegram -->
      <a
        href="https://t.me/wirebackcore"
        target="_blank"
        rel="noopener noreferrer"
        class="glitch-button flex items-center justify-center gap-3 px-6 py-3 text-lg rounded"
      >
        <img src="/icons/telegram.svg" alt="Telegram" class="w-5 h-5" />
        Join Telegram
      </a>
    </div>
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
