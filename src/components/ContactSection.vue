<script setup>
import { ref } from 'vue'

const form = ref({
  name: '',
  email: '',
  message: ''
})
const submitted = ref(false)

const handleSubmit = () => {
  if (form.value.name && form.value.email && form.value.message) {
    submitted.value = true
    setTimeout(() => {
      submitted.value = false
      form.value = { name: '', email: '', message: '' }
    }, 3000)
  }
}
</script>

<template>
  <section id="contact" class="relative py-24 px-6 bg-gradient-to-b from-deep to-steel/30">
    <div class="max-w-4xl mx-auto">
      <div class="text-center mb-12 reveal">
        <div class="font-mono text-xs text-bio tracking-[0.3em] mb-4">// ESTABLISH_LINK</div>
        <h2 class="font-cyber font-bold text-4xl md:text-5xl chrome-text mb-4">
          TRANSMIT SIGNAL
        </h2>
        <p class="font-mono text-chrome/60 max-w-xl mx-auto">
          Open a direct channel to the Techfest mainframe. We'll respond within 24 hours.
        </p>
      </div>

      <div class="glass-card p-8 md:p-12 reveal hud-bracket">
        <!-- Success state -->
        <div v-if="submitted" class="text-center py-12">
          <div class="text-6xl mb-4">✓</div>
          <div class="font-cyber text-2xl text-neural mb-2">TRANSMISSION RECEIVED</div>
          <div class="font-mono text-sm text-chrome/60">Your signal has been logged. Stand by...</div>
        </div>

        <!-- Form -->
        <form v-else @submit.prevent="handleSubmit" class="space-y-6">
          <div class="grid md:grid-cols-2 gap-6">
            <div>
              <label class="block font-mono text-xs text-neural tracking-widest mb-2">&gt; IDENTIFIER</label>
              <input 
                v-model="form.name"
                type="text" 
                required
                class="w-full px-4 py-3 bg-deep/50 border border-neural/30 text-chrome font-mono focus:outline-none focus:border-neural focus:shadow-[0_0_15px_rgba(0,240,255,0.3)] transition-all"
                placeholder="Enter your name"
              />
            </div>
            <div>
              <label class="block font-mono text-xs text-neural tracking-widest mb-2">&gt; NEURAL_ADDRESS</label>
              <input 
                v-model="form.email"
                type="email" 
                required
                class="w-full px-4 py-3 bg-deep/50 border border-neural/30 text-chrome font-mono focus:outline-none focus:border-neural focus:shadow-[0_0_15px_rgba(0,240,255,0.3)] transition-all"
                placeholder="your@email.com"
              />
            </div>
          </div>

          <div>
            <label class="block font-mono text-xs text-neural tracking-widest mb-2">&gt; PAYLOAD</label>
            <textarea 
              v-model="form.message"
              rows="5"
              required
              class="w-full px-4 py-3 bg-deep/50 border border-neural/30 text-chrome font-mono focus:outline-none focus:border-neural focus:shadow-[0_0_15px_rgba(0,240,255,0.3)] transition-all resize-none"
              placeholder="Transmit your message..."
            ></textarea>
          </div>

          <button 
            type="submit"
            class="cyber-btn w-full py-4 bg-gradient-to-r from-neural to-bio text-deep font-cyber font-bold tracking-[0.3em] hover:shadow-[0_0_40px_rgba(0,240,255,0.5)] transition-all"
          >
            EXECUTE_TRANSMISSION
          </button>
        </form>
      </div>

      <!-- Social links -->
      <div class="flex justify-center gap-6 mt-12 reveal">
        <a href="#" class="w-12 h-12 border border-neural/30 flex items-center justify-center hover:border-neural hover:bg-neural/10 hover:shadow-[0_0_15px_rgba(0,240,255,0.4)] transition-all">
          <span class="font-mono text-neural">TW</span>
        </a>
        <a href="#" class="w-12 h-12 border border-neural/30 flex items-center justify-center hover:border-neural hover:bg-neural/10 hover:shadow-[0_0_15px_rgba(0,240,255,0.4)] transition-all">
          <span class="font-mono text-neural">IG</span>
        </a>
        <a href="#" class="w-12 h-12 border border-neural/30 flex items-center justify-center hover:border-neural hover:bg-neural/10 hover:shadow-[0_0_15px_rgba(0,240,255,0.4)] transition-all">
          <span class="font-mono text-neural">LI</span>
        </a>
        <a href="#" class="w-12 h-12 border border-neural/30 flex items-center justify-center hover:border-neural hover:bg-neural/10 hover:shadow-[0_0_15px_rgba(0,240,255,0.4)] transition-all">
          <span class="font-mono text-neural">GH</span>
        </a>
      </div>
    </div>
  </section>
</template>