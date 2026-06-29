<script setup>
import { ref, onMounted } from 'vue'
const statusText = ref('')
const fullText = '> INITIALIZING NEURAL INTERFACE...'

onMounted(() => {
  let i = 0
  const type = () => {
    if (i < fullText.length) {
      statusText.value += fullText.charAt(i)
      i++
      setTimeout(type, 50)
    }
  }
  type()
})
</script>

<template>
  <section id="home" class="relative min-h-screen flex items-center justify-center overflow-hidden circuit-grid">
    <!-- Animated background blobs -->
    <div class="absolute inset-0 vein-pattern"></div>
    <div class="absolute top-1/4 left-1/4 w-96 h-96 bg-neural/20 rounded-full blur-3xl animate-pulse-slow"></div>
    <div class="absolute bottom-1/4 right-1/4 w-96 h-96 bg-bio/20 rounded-full blur-3xl animate-pulse-slow" style="animation-delay: 2s"></div>

    <!-- Content -->
    <div class="relative z-10 max-w-6xl mx-auto px-6 pt-24 grid md:grid-cols-2 gap-12 items-center">
      <!-- Left: Text -->
      <div>
        <div class="inline-flex items-center gap-2 px-4 py-1 border border-neural/40 rounded-full mb-6 bg-neural/5">
          <span class="w-2 h-2 bg-bio rounded-full animate-pulse"></span>
          <span class="font-mono text-xs text-neural tracking-widest">SYSTEM ONLINE // v2.026</span>
        </div>

        <h1 class="font-cyber font-black text-5xl md:text-7xl leading-tight mb-6">
          <span class="block chrome-text">AUGMENT</span>
          <span class="block chrome-text">YOUR</span>
          <span class="block neon-text text-neural">REALITY</span>
        </h1>

        <p class="font-mono text-chrome/70 text-lg mb-4 max-w-md">
          The future isn't coming — it's being <span class="text-bio">built</span>. 
          Step into Techfest IIT Bombay, where humans merge with machines.
        </p>

        <p class="font-mono text-xs text-neural mb-8 h-4">
          {{ statusText }}<span class="animate-pulse">▊</span>
        </p>

        <div class="flex flex-wrap gap-4">
          <a href="#features" class="cyber-btn px-8 py-3 bg-neural text-deep font-cyber font-bold tracking-widest hover:shadow-[0_0_30px_rgba(0,240,255,0.6)]">
            EXPLORE MODULES
          </a>
          <a href="#about" class="cyber-btn px-8 py-3 border-2 border-bio text-bio font-cyber font-bold tracking-widest hover:bg-bio hover:text-deep">
            LEARN MORE
          </a>
        </div>

        <!-- Stats row -->
        <div class="mt-12 grid grid-cols-3 gap-4 max-w-md">
          <div>
            <div class="font-cyber font-bold text-2xl text-neural">50K+</div>
            <div class="font-mono text-xs text-chrome/50">PARTICIPANTS</div>
          </div>
          <div>
            <div class="font-cyber font-bold text-2xl text-bio">200+</div>
            <div class="font-mono text-xs text-chrome/50">EVENTS</div>
          </div>
          <div>
            <div class="font-cyber font-bold text-2xl text-neural">72H</div>
            <div class="font-mono text-xs text-chrome/50">NON-STOP</div>
          </div>
        </div>
      </div>

      <!-- Right: Cyborg Visual -->
      <div class="relative flex items-center justify-center animate-float">
        <!-- Outer ring -->
        <div class="absolute w-80 h-80 md:w-96 md:h-96 border-2 border-neural/30 rounded-full animate-spin" style="animation-duration: 20s"></div>
        <div class="absolute w-72 h-72 md:w-80 md:h-80 border border-bio/30 rounded-full animate-spin" style="animation-duration: 15s; animation-direction: reverse"></div>
        
        <!-- Center cyborg head SVG -->
        <div class="relative w-64 h-64 md:w-80 md:h-80 hud-bracket flex items-center justify-center">
          <svg viewBox="0 0 200 200" class="w-full h-full drop-shadow-[0_0_20px_rgba(0,240,255,0.5)]">
            <!-- Head outline -->
            <path d="M100 30 C60 30 40 70 40 110 C40 140 55 170 100 175 C145 170 160 140 160 110 C160 70 140 30 100 30 Z" 
                  fill="none" stroke="#00f0ff" stroke-width="1.5" opacity="0.8"/>
            <!-- Circuit lines -->
            <path d="M60 80 L80 80 L80 100 M140 80 L120 80 L120 100" stroke="#00f0ff" stroke-width="1" fill="none" opacity="0.6"/>
            <!-- Left eye (organic) -->
            <circle cx="75" cy="95" r="8" fill="none" stroke="#ff2d75" stroke-width="1.5"/>
            <circle cx="75" cy="95" r="3" fill="#ff2d75"/>
            <!-- Right eye (cybernetic) -->
            <rect x="115" y="87" width="20" height="16" fill="none" stroke="#00f0ff" stroke-width="1.5"/>
            <line x1="115" y1="95" x2="135" y2="95" stroke="#00f0ff" stroke-width="1"/>
            <circle cx="125" cy="95" r="2" fill="#00f0ff" class="animate-pulse"/>
            <!-- Jaw plate -->
            <path d="M70 130 L130 130 L125 150 L75 150 Z" fill="none" stroke="#00f0ff" stroke-width="1" opacity="0.7"/>
            <!-- Neck connectors -->
            <line x1="85" y1="175" x2="85" y2="190" stroke="#00f0ff" stroke-width="1"/>
            <line x1="115" y1="175" x2="115" y2="190" stroke="#00f0ff" stroke-width="1"/>
            <!-- Data points -->
            <circle cx="50" cy="110" r="2" fill="#00f0ff" class="animate-pulse"/>
            <circle cx="150" cy="110" r="2" fill="#ff2d75" class="animate-pulse"/>
          </svg>

          <!-- Floating HUD labels -->
          <div class="absolute top-0 -right-4 font-mono text-[10px] text-neural">
            <div>SYS: OK</div>
            <div>NEURAL: 98%</div>
          </div>
          <div class="absolute bottom-0 -left-4 font-mono text-[10px] text-bio text-right">
            <div>BIO: STABLE</div>
            <div>SYNC: ACTIVE</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Scroll indicator -->
    <div class="absolute bottom-8 left-1/2 -translate-x-1/2 flex flex-col items-center gap-2">
      <span class="font-mono text-xs text-neural/60 tracking-widest">SCROLL</span>
      <div class="w-px h-12 bg-gradient-to-b from-neural to-transparent animate-pulse"></div>
    </div>
  </section>
</template>