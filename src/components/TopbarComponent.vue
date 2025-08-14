<template>
  <header
    class="fixed top-0 inset-x-0 z-50"
  >
    <nav class="w-full px-6 sm:px-8 md:px-12 lg:px-16 h-16 pt-8 flex items-center justify-between text-white">
      

      <!-- Left: Brand -->
      <button
        class="font-display text-2xl tracking-wide hover:glitch-hover transition-colors"
        @click="scrollTop"
        aria-label="Go to top"
      >
        WIREBACK
      </button>

      <!-- Right: Section links -->
      <div class="flex items-center gap-5">
        <button class="px-2 py-1 text-xl hover:glitch-hover transition-colors"
                @click="go('TokenomicsComponent')">
          Tokenomics
        </button>
        <button class="px-2 py-1 text-xl hover:glitch-hover transition-colors"
                @click="go('LoreComponent')">
          Lore
        </button>
        <button class="px-2 py-1 text-xl hover:glitch-hover transition-colors"
                @click="go('BuyComponent')">
          Where to Buy
        </button>
        <button class="px-2 py-1 text-xl hover:glitch-hover transition-colors"
                @click="go('SocialsComponent')">
          Socials
        </button>
      </div>
    </nav>
  </header>
</template>

<script setup lang="ts">

function scrollTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' });
}

const HEADER_H = 64;
const EXTRA = 64; // push under the header a little more
function go(id: string) {
  const el = document.getElementById(id);
  if (!el) return;
  const y = el.getBoundingClientRect().top + window.scrollY - HEADER_H + EXTRA;
  window.scrollTo({ top: Math.max(y, 0), behavior: 'smooth' });
}

</script>

<style scoped>
/* Glitch effect only when hovering */
.hover\:glitch-hover:hover {
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
