<template>
  <section class="py-16 px-4 text-white text-center bg-lore">

    <h2 class="text-4xl md:text-5xl font-bold glitch-text mb-8">The Lore</h2>

    <p class="max-w-2xl mx-auto text-lg md:text-xl leading-relaxed">
      From the ashes of burned-out NPCs, a new protocol was uploaded. <span class="glitch-highlight">$WIREBACK</span> is the 
      final form of Wojak — corrupted by AI, patched by memes, and deployed on Solana. 
      He's not just self-aware... he's self-shilling.
    </p>
  </section>
</template>

<script setup lang="ts">
// No script needed for static section
</script>

<style scoped>

.bg-lore {
  background: radial-gradient(ellipse at center, #3a003f 10%, #000000 90%);
}


.glitch-text {
  position: relative;
  color: #0ff;
  text-shadow: 2px 0 red, -2px 0 blue;
  animation: glitch-flicker 2s infinite linear;
}

.glitch-highlight {
  color: #0ff;
  text-shadow: 1px 0 red, -1px 0 blue;
  animation: glitch-glow 1s infinite linear;
}

@keyframes glitch-flicker {
  0% { text-shadow: 2px 0 red, -2px 0 blue; }
  50% { text-shadow: -2px 0 red, 2px 0 blue; }
  100% { text-shadow: 2px 0 red, -2px 0 blue; }
}

@keyframes glitch-glow {
  0% { text-shadow: 0 0 4px #0ff; }
  50% { text-shadow: 0 0 8px red, 0 0 8px blue; }
  100% { text-shadow: 0 0 4px #0ff; }
}
</style>
