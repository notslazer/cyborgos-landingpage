<script setup>
const modules = [
  {
    icon: '⚙',
    title: 'ROBOTICS ARENA',
    code: 'MOD_01',
    desc: 'Autonomous machines. Battle bots. Neural-controlled mechs. Witness the evolution of mechanical life.',
    color: 'neural'
  },
  {
    icon: '◈',
    title: 'CODE WARS',
    code: 'MOD_02',
    desc: '48-hour hackathons. Algorithmic duels. Build the software that will power the next generation of cyborgs.',
    color: 'bio'
  },
  {
    icon: '⬢',
    title: 'AI NEXUS',
    code: 'MOD_03',
    desc: 'Deep learning labs. Generative AI showcases. See machines that think, create, and evolve.',
    color: 'neural'
  },
  {
    icon: '◉',
    title: 'BIOTECH LAB',
    code: 'MOD_04',
    desc: 'Where biology meets circuitry. Neural interfaces, prosthetics, and the future of human enhancement.',
    color: 'bio'
  },
  {
    icon: '▲',
    title: 'AERO DOME',
    code: 'MOD_05',
    desc: 'Drones, rockets, and aerial combat. Engineering that defies gravity and pushes boundaries.',
    color: 'neural'
  },
  {
    icon: '◆',
    title: 'DESIGN FORGE',
    code: 'MOD_06',
    desc: 'UI/UX battles, product sprints, and creative hackathons. Design the interfaces of tomorrow.',
    color: 'bio'
  },
]
</script>

<template>
  <section id="features" class="relative py-24 px-6 bg-gradient-to-b from-deep via-steel/30 to-deep">
    <div class="max-w-7xl mx-auto">
      <!-- Section header -->
      <div class="text-center mb-16 reveal">
        <div class="inline-block font-mono text-xs text-bio tracking-[0.3em] mb-4">// CORE_MODULES</div>
        <h2 class="font-cyber font-bold text-4xl md:text-6xl chrome-text mb-4">
          AUGMENTATION MODULES
        </h2>
        <p class="font-mono text-chrome/60 max-w-xl mx-auto">
          Select your upgrade path. Each module unlocks a new dimension of technological mastery.
        </p>
      </div>

      <!-- Modules grid -->
      <div class="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
        <div 
          v-for="(mod, idx) in modules" 
          :key="idx"
          class="glass-card p-6 reveal hud-bracket group"
        >
          <!-- Code tag -->
          <div class="flex items-center justify-between mb-4">
            <span class="font-mono text-xs text-chrome/40">{{ mod.code }}</span>
            <span 
              class="w-2 h-2 rounded-full animate-pulse"
              :class="mod.color === 'neural' ? 'bg-neural' : 'bg-bio'"
            ></span>
          </div>

          <!-- Icon -->
          <div 
            class="text-5xl mb-4 transition-transform duration-500 group-hover:scale-110 group-hover:rotate-6"
            :class="mod.color === 'neural' ? 'text-neural' : 'text-bio'"
          >
            {{ mod.icon }}
          </div>

          <!-- Title -->
          <h3 
            class="font-cyber font-bold text-xl mb-3 tracking-wider"
            :class="mod.color === 'neural' ? 'text-neural' : 'text-bio'"
          >
            {{ mod.title }}
          </h3>

          <!-- Description -->
          <p class="font-mono text-sm text-chrome/70 leading-relaxed mb-4">
            {{ mod.desc }}
          </p>

          <!-- Action -->
          <a href="#" class="inline-flex items-center gap-2 font-mono text-xs tracking-widest text-chrome/50 group-hover:text-neural transition-colors">
            <span>ACCESS_MODULE</span>
            <span class="transition-transform group-hover:translate-x-1">→</span>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>