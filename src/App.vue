<script>
import Hero from './components/Hero.vue'
import Tokenomics from './components/Tokenomics.vue'
import Lore from './components/Lore.vue'
import Socials from './components/Socials.vue'
import Buy from './components/Buy.vue'

export default {
  components: {
    Hero,
    Tokenomics,
    Lore,
    Socials,
    Buy,
  }
}
</script>

<template>
  <main class="bg-black text-white">
    <Hero />
    <Tokenomics />
    <Lore />
    <Socials />
    <Buy />
  </main>
</template>