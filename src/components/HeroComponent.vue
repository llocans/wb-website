<template>
  <section
    id="HeroComponent"
    class="hero-bg min-h-screen text-white text-center px-4 relative -mt-16"
  >
    <!-- offset content down by header height so it isn't covered -->
    <div class="pt-16 flex flex-col justify-center items-center min-h-screen">
      <img
        :src="logo"
        alt="Wireback Logo"
        class="w-40 md:w-60 object-contain mb-8 drop-shadow-[0_0_15px_rgba(128,0,255,0.6)]"
      />

      <h1 class="glitch-text text-5xl md:text-7xl font-bold tracking-wider">
        $WIREBACK
      </h1>

      <p class="mt-6 text-xl md:text-2xl text-gray-300 max-w-lg">
        Code can't feel. Humans can.
      </p>
      <p class="mt-2 text-xl md:text-2xl text-gray-300 max-w-lg">
        Stay human, stay free.
      </p>
    </div>
  </section>
</template>


<script setup lang="ts">
import logo from '@/assets/img/wojak.png'
</script>

<style scoped>
.hero-bg {
  background-image: url('@/assets/img/m5.jpg');
  background-size: cover;
  background-repeat: repeat-x;
  background-position: 0 0;
  animation: scroll-bg 20s linear infinite alternate;
}

@keyframes scroll-bg {
  0% {
    background-position: left;
  }
  100% {
    background-position: right;
  }
}

/* Glitch styling from previous step */
.glitch-text {
  position: relative;
  color: #0ff;
  text-shadow: 3px 0 red, -3px 0 blue, 0 2px lime;
  animation: glitch-flicker 2s infinite linear;
}

.glitch-text::before,
.glitch-text::after {
  content: attr(class);
  position: absolute;
  left: 0;
  width: 100%;
  overflow: hidden;
  color: #0ff;
  z-index: -1;
}

.glitch-text::before {
  top: -2px;
  text-shadow: -3px 0 magenta;
  animation: glitch-before 1.5s infinite linear;
}

.glitch-text::after {
  top: 2px;
  text-shadow: 3px 0 cyan;
  animation: glitch-after 1.2s infinite linear;
}

@keyframes glitch-flicker {
  0% { text-shadow: 3px 0 red, -3px 0 blue, 0 2px lime; }
  15% { text-shadow: -4px -2px red, 4px 2px blue, 0 0 lime; }
  30% { text-shadow: 5px 0 red, -5px 0 blue, 0 4px lime; }
  45% { text-shadow: -2px 2px red, 2px -2px blue, 0 0 lime; }
  60% { text-shadow: 4px -2px red, -4px 2px blue, 0 2px lime; }
  75% { text-shadow: -1px -1px red, 1px 1px blue, 0 -2px lime; }
  100% { text-shadow: 3px 0 red, -3px 0 blue, 0 2px lime; }
}

@keyframes glitch-before {
  0% { clip-path: inset(0% 0 80% 0); }
  50% { clip-path: inset(20% 0 50% 0); transform: translateX(-3px); }
  100% { clip-path: inset(10% 0 60% 0); transform: translateX(0); }
}

@keyframes glitch-after {
  0% { clip-path: inset(50% 0 20% 0); }
  50% { clip-path: inset(30% 0 40% 0); transform: translateX(3px); }
  100% { clip-path: inset(60% 0 10% 0); transform: translateX(0); }
}
</style>
