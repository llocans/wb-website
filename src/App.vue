<script setup lang="ts">
import HeroComponent from './components/HeroComponent.vue'
import TokenomicsComponent from './components/TokenomicsComponent.vue'
import LoreComponent from './components/LoreComponent.vue'
import SocialsComponent from './components/SocialsComponent.vue'
import BuyComponent from './components/BuyComponent.vue'
import TopBarComponent from './components/TopBarComponent.vue'
import ScrollToTopComponent from './components/ScrollToTopComponent.vue'
</script>

<template>
  <main class="bg-black text-white">
    <TopBarComponent />
    <HeroComponent />
    <TokenomicsComponent />
    <LoreComponent />
    <BuyComponent />
    <SocialsComponent />

  </main>
  <ScrollToTopComponent />
</template>
