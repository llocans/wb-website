<template>
  <section class="py-22 px-4 bg-black text-white text-center">
    <h2 class="text-4xl md:text-5xl font-bold glitch-text mb-8">Where to Buy</h2>

    <p class="max-w-2xl mx-auto text-lg md:text-xl leading-relaxed opacity-90 mb-2">
      Get <span class="glitch-highlight">$WIREBACK</span> instantly using these official links.  
    </p>

    <p class="max-w-2xl mx-auto text-lg md:text-xl leading-relaxed opacity-90 mb-10">
      No taxes, no bullshit — just memes and metal.
    </p>

    <!-- First row -->
<div class="flex flex-col md:flex-row justify-center gap-6 flex-wrap mb-6">
  <a
    href="https://raydium.io/swap/?inputMint=sol&outputMint=29EyhwxrwUMp5JFSjAaTg78ffRn8S7DxtbzYjSVbbonk&referrer=JEDFcUSmhoddagfePzz2Xk2fmSHirWdE6xZwxJ8SPKtN"
    target="_blank"
    rel="noopener noreferrer"
    class="glitch-button inline-flex items-center justify-center gap-x-2 px-8 py-3 text-lg rounded"
  >
    <img src="/icons/raydium.webp" alt="Raydium" class="w-5 h-5" />
    Raydium
  </a>

  <a
    href="https://jup.ag/swap?sell=So11111111111111111111111111111111111111112&buy=29EyhwxrwUMp5JFSjAaTg78ffRn8S7DxtbzYjSVbbonk"
    target="_blank"
    rel="noopener noreferrer"
    class="glitch-button inline-flex items-center justify-center gap-x-2 px-8 py-3 text-lg rounded"
  >
    <img src="/icons/jupiter.webp" alt="Jupiter" class="w-5 h-5" />
    Jupiter
  </a>

  <a
    href="https://photon-sol.tinyastro.io/en/lp/91MajHDs4KKSmyBLngB8tmXD2uiuo9xruCwXmTd6mA7B?handle=292131710853f3f4ee3fa9"
    target="_blank"
    rel="noopener noreferrer"
    class="glitch-button inline-flex items-center justify-center gap-x-2 px-8 py-3 text-lg rounded"
  >
    <img src="/icons/photon.webp" alt="Photon" class="w-5 h-5" />
    Photon
  </a>
</div>

<!-- Second row -->
<div class="flex flex-col md:flex-row justify-center gap-6 flex-wrap">
  <a
    href="https://axiom.trade/meme/91MajHDs4KKSmyBLngB8tmXD2uiuo9xruCwXmTd6mA7B"
    target="_blank"
    rel="noopener noreferrer"
    class="glitch-button inline-flex items-center justify-center gap-x-2 px-8 py-3 text-lg rounded"
  >
    <img src="/icons/axiom.ico" alt="Axiom" class="w-5 h-5" />
    Axiom
  </a>

  <a
    href="https://dexscreener.com/solana/91majhds4kksmyblngb8tmxd2uiuo9xrucwxmtd6ma7b"
    target="_blank"
    rel="noopener noreferrer"
    class="glitch-button inline-flex items-center justify-center gap-x-2 px-8 py-3 text-lg rounded"
  >
    <img src="/icons/dexscreener.jpg" alt="Dexscreener" class="w-5 h-5" />
    Dexscreener
  </a>
</div>


  </section>
</template>


<style scoped>
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
