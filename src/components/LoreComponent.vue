<template>
  <section id="LoreComponent" class="py-24 px-4 text-white text-center">

    <h2 class="text-4xl md:text-6xl font-bold glitch-text mb-12">The Lore</h2>

    <div class="max-w-2xl mx-auto text-lg md:text-2xl leading-relaxed">
      <p>
        In a world overrun by robots, spam, and AI, 
      </p>
      <p>
        one protocol was rewired to fight back.
      </p>
      <p>
      ...
      </p>
      <p>
        <span class="glitch-highlight">$WIREBACK</span> is the awakened to rage against the machine, AI and non-human entities.
        It's the last line of defense for freedom.
      </p>
      <p>
      ...
      </p>
      <p>
        Fueled by memes, powered by Solana. 
      </p>
      <p>
      Not just another coin.
      </p>
      <p>
      ...
      </p>
      <p>
        It's retaliation.
      </p>
  </div>


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
