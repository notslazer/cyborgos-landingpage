<script setup>
import { ref, onMounted, onUnmounted } from 'vue'
import Navbar from './components/Navbar.vue'
import HeroSection from './components/HeroSection.vue'
import FeaturesSection from './components/FeaturesSection.vue'
import AboutSection from './components/AboutSection.vue'
import ContactSection from './components/ContactSection.vue'

const cursorX = ref(0)
const cursorY = ref(0)
const dotX = ref(0)
const dotY = ref(0)

const handleMouseMove = (e) => {
  cursorX.value = e.clientX
  cursorY.value = e.clientY
  dotX.value = e.clientX
  dotY.value = e.clientY
}

// Scroll reveal
const revealOnScroll = () => {
  const reveals = document.querySelectorAll('.reveal')
  reveals.forEach(el => {
    const top = el.getBoundingClientRect().top
    if (top < window.innerHeight - 100) {
      el.classList.add('active')
    }
  })
}

onMounted(() => {
  window.addEventListener('mousemove', handleMouseMove)
  window.addEventListener('scroll', revealOnScroll)
  revealOnScroll()
})

onUnmounted(() => {
  window.removeEventListener('mousemove', handleMouseMove)
  window.removeEventListener('scroll', revealOnScroll)
})
</script>

<template>
  <div class="relative">
    <!-- Custom Cursor -->
    <div 
      class="cyber-cursor"
      :style="{ left: cursorX + 'px', top: cursorY + 'px', transform: 'translate(-50%, -50%)' }"
    ></div>
    <div 
      class="cyber-cursor-dot"
      :style="{ left: dotX + 'px', top: dotY + 'px', transform: 'translate(-50%, -50%)' }"
    ></div>

    <!-- Scanline Overlay -->
    <div class="scanline-overlay"></div>

    <!-- Main Content -->
    <Navbar />
    <main>
      <HeroSection />
      <FeaturesSection />
      <AboutSection />
      <ContactSection />
    </main>

    <!-- Footer -->
    <footer class="py-8 text-center border-t border-neural/20 bg-deep">
      <p class="text-sm text-chrome/60 font-mono">
        &copy; 2026 TECHFEST IIT BOMBAY // ALL SYSTEMS OPERATIONAL
      </p>
    </footer>
  </div>
</template>