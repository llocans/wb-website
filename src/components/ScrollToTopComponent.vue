<template>
  <button
    v-show="visible"
    @click="scrollTop"
    class="fixed bottom-6 right-8 p-4 rounded-full bg-black/60 text-white border border-cyan-400/40 shadow-[0_0_15px_rgba(0,255,255,0.4)] hover:shadow-[0_0_25px_rgba(0,255,255,0.7)] transition duration-300 matrix-hover"
    aria-label="Scroll to top"
  >
    BACK TO TOP
  </button>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount } from 'vue'

const visible = ref(false)

function onScroll() {
  visible.value = window.scrollY > 200
}

function scrollTop() {
  window.scrollTo({ top: 0, behavior: 'smooth' })
}

onMounted(() => {
  window.addEventListener('scroll', onScroll)
})

onBeforeUnmount(() => {
  window.removeEventListener('scroll', onScroll)
})
</script>

<style scoped>
/* Matches topbar "Matrix" hover effect */
.matrix-hover:hover {
  text-shadow:
    0 0 6px rgba(0, 255, 255, 0.7),
    0 0 12px rgba(0, 255, 170, 0.5),
    1px 0 0 rgba(0, 255, 0, 0.6),
    -1px 0 0 rgba(0, 170, 255, 0.6);
  animation: matrix-jitter 0.35s infinite alternate;
}

@keyframes matrix-jitter {
  0%   { transform: translate(0, 0); }
  50%  { transform: translate(0.2px, -0.2px) skewX(0.3deg); }
  100% { transform: translate(-0.2px, 0.2px) skewX(-0.3deg); }
}
</style>
