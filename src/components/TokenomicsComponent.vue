<template>
  <section class="py-18 px-4 bg-black text-white text-center">
    <h2 class="text-4xl md:text-5xl font-bold glitch-text mb-10">Tokenomics</h2>

    <div class="grid gap-6 md:grid-cols-3 max-w-4xl mx-auto">
      <div class="token-box">Total Supply<br /><span class="token-value">1,000,000,000</span></div>
      <div class="token-box">Buy Tax<br /><span class="token-value">0%</span></div>
      <div class="token-box">Ticker<br /><span class="token-value">$WIREBACK</span></div>
      <div class="token-box">Liquidity Locked<br /><span class="token-value">Yes</span></div>
      <div class="token-box">Ownership<br /><span class="token-value">Renounced</span></div>
      <div class="token-box">Chain<br /><span class="token-value">Solana</span></div>

      <!-- Full-width box for contract address -->
      <div class="md:col-span-3 token-box flex flex-col items-center text-center">
        <span class="break-all text-sm md:text-base text-white">
          {{ address }}
        </span>

        <button
          @click="copyAddress"
          class="mt-4 px-5 py-2 glitch-button text-white text-sm rounded relative overflow-hidden"
          >
          {{ copied ? 'Copied!' : 'Copy Coin Address' }}
        </button>

      </div>
    </div>

    <!-- <p class="text-gray-400 mt-10 text-sm italic">
      * Real-time stats coming soon
    </p> -->
  </section>
</template>

<script setup lang="ts">
import { ref } from 'vue'

const address = '29EyhwxrwUMp5JFSjAaTg78ffRn8S7DxtbzYjSVbbonk'
const copied = ref(false)

function copyAddress() {
  navigator.clipboard.writeText(address).then(() => {
    copied.value = true
    setTimeout(() => {
      copied.value = false
    }, 1500)
  })
}


</script>

<style scoped>
.bg-gradient-tokenomics {
  background: linear-gradient(to bottom, #00ffff 0%, #001f3f 50%, #000000 100%);
}

  .glitch-button {
    background: #0ff;
    color: black;
    font-weight: bold;
    letter-spacing: 0.05em;
    border: 1px solid #0ff;
    box-shadow: 0 0 10px #0ff;
    transition: all 0.3s ease-in-out;
  }

  .glitch-button:hover {
    background: black;
    color: #0ff;
    animation: glitch-glow 0.3s infinite;
  }

  @keyframes glitch-glow {
    0% { box-shadow: 0 0 5px #0ff; }
    50% { box-shadow: 0 0 15px #0ff, 0 0 5px red, 0 0 5px blue; }
    100% { box-shadow: 0 0 5px #0ff; }
  }

  /* Glitch effect for the title */
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

  .token-box {
    background-color: rgba(255, 255, 255, 0.05);
    padding: 1.5rem;
    border-radius: 1rem;
    border: 1px solid rgba(255, 255, 255, 0.1);
    font-size: 1.2rem;
    font-weight: 600;
    transition: transform 0.3s ease;
  }
  .token-box:hover {
    transform: scale(1.05);
    border-color: #0ff;
  }

  .token-value {
    display: block;
    margin-top: 0.5rem;
    font-size: 1.5rem;
    color: #0ff;
  }

</style>
