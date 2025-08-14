<template>
  <section id="TokenomicsComponent" class="py-26 px-4 text-white text-center">
    <h2 class="text-4xl md:text-5xl font-bold glitch-text mb-12">Tokenomics</h2>

    <div class="grid gap-6 md:grid-cols-3 max-w-4xl mx-auto">
      <!-- 1) Total Supply (static) -->
      <div class="token-box">
        Total Supply<br />
        <span class="token-value">1,000,000,000</span>
      </div>

      <!-- 2) Market Cap (USD) replacing Buy Tax -->
      <div class="token-box">
        Market Cap (USD)<br />
        <span class="token-value">
          <template v-if="marketCapUsd !== null">{{ fmtUSD(marketCapUsd) }}</template>
          <template v-else>—</template>
        </span>
      </div>

      <!-- 3) Ticker -->
      <div class="token-box">
        Ticker<br />
        <span class="token-value">$WIREBACK</span>
      </div>

      <!-- 4) Liquidity Locked -->
      <div class="token-box">
        Liquidity Locked<br />
        <span class="token-value">Yes</span>
      </div>

      <!-- 5) Buy Tax (moved to Ownership’s slot) -->
      <div class="token-box">
        Buy Tax<br />
        <span class="token-value">0%</span>
      </div>

      <!-- 6) Chain -->
      <div class="token-box">
        Chain<br />
        <span class="token-value">Solana</span>
      </div>

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
  </section>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

const address = '29EyhwxrwUMp5JFSjAaTg78ffRn8S7DxtbzYjSVbbonk';
const copied = ref(false);

function copyAddress() {
  navigator.clipboard.writeText(address).then(() => {
    copied.value = true;
    setTimeout(() => (copied.value = false), 1500);
  });
}

/* ---- Live data: price only ---- */
const SUPPLY_FIXED = 1_000_000_000; // static supply
const PRICE_URL  = 'https://wb-api-usdprice.tokeninfo.workers.dev/';

const price  = ref<number | null>(null);
const marketCapUsd = ref<number | null>(null);
const updatedAt = ref<Date | null>(null);

function fmtUSD(n: number) {
  if (n >= 1_000_000) {
    const units = ['K', 'M', 'B', 'T'];
    let u = -1, x = n;
    while (x >= 1000 && u < units.length - 1) { x /= 1000; u++; }
    return `$${x.toFixed(2)}${units[u]}`;
  }
  return new Intl.NumberFormat('en-US', { style: 'currency', currency: 'USD', maximumFractionDigits: 2 }).format(n);
}

async function load() {
  try {
    const pRes = await fetch(PRICE_URL, { cache: 'no-store' });
    const p = Number((await pRes.text()).trim());

    price.value  = Number.isFinite(p) ? p : null;

    marketCapUsd.value =
      price.value !== null
        ? +(SUPPLY_FIXED * price.value).toFixed(2)
        : null;

    updatedAt.value = new Date();
  } catch {
    // leave values as-is; UI shows “—” on nulls
  }
}

onMounted(() => {
  load();
});
</script>

<style scoped>
.bg-gradient-tokenomics {
  background: linear-gradient(to bottom, #00ffff 0%, #001f3f 50%, #000000 100%);
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

.glitch-text {
  position: relative;
  color: #0ff;
  text-shadow: 2px 0 red, -2px 0 blue;
  animation: glitch-flicker 2s infinite linear;
}
@keyframes glitch-flicker {
  0% { text-shadow: 2px 0 red, 2px 0 blue; }
  50% { text-shadow: -2px 0 red, -2px 0 blue; }
  100% { text-shadow: 2px 0 red, 2px 0 blue; }
}

.token-box {
  background-color: rgba(255, 255, 255, 0.05);
  padding: 1.5rem;
  border-radius: 1rem;
  border: 1px solid rgba(255, 255, 255, 0.1);
  font-size: 1.2rem;
  font-weight: 600;
  transition: transform 0.3s ease;

  backdrop-filter: blur(6px);
  -webkit-backdrop-filter: blur(6px);
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
