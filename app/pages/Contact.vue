<template>
  <div class="bg-black text-white min-h-screen overflow-hidden">
    
    <!-- Hero Header -->
    <section class="h-[50vh] flex items-center justify-center relative select-none">
      <div class="absolute inset-0 z-0">
        <img
          :src="bg"
          class="w-full h-full object-cover opacity-40 filter contrast-125 transition-all duration-1000 transform hover:scale-105"
          alt="SabAli Contact Header Background"
        />
        <div class="absolute inset-0 bg-gradient-to-b from-black/80 via-black/40 to-black"></div>
      </div>

      <div class="relative z-10 text-center px-6 max-w-4xl">
        <span class="text-xs uppercase tracking-[0.5em] text-white/50 block mb-6 animate-fade-in">
          {{ $t('contact.hero_sub') }}
        </span>
        <h1 class="text-4xl md:text-7xl font-light tracking-[0.15em] text-white uppercase leading-none mb-4">
          {{ $t('contact.hero_title') }}
        </h1>
        <p class="text-sm font-serif italic text-white/60 tracking-[0.2em] leading-relaxed max-w-md mx-auto">
          {{ $t('contact.hero_desc') }}
        </p>
      </div>
    </section>

    <!-- Contact & Form Section -->

    <section class="py-24 px-6 sm:px-12 md:px-24 bg-black border-t border-white/5 relative">
      <div class="max-w-7xl mx-auto grid lg:grid-cols-12 gap-16">
        
        <!-- Left: Boutique Coordinates -->
        <div class="lg:col-span-5 flex flex-col space-y-12">
          
          <div class="space-y-4">
            <h2 class="text-xs uppercase tracking-[0.4em] text-white/40">
              {{ $t('contact.boutiques_title') }}
            </h2>
            <div class="h-[1px] w-12 bg-white/20"></div>
          </div>

          <!-- Locations -->
          <div class="space-y-8">

            <!-- Tashkent -->
            <div class="flex flex-col space-y-2">
              <span class="text-sm font-semibold tracking-widest text-white uppercase">{{ $t('contact.tashkent_title') }}</span>
              <p class="text-sm text-white/60 font-light leading-relaxed">
                {{ $t('contact.tashkent_addr') }}
              </p>
              <p class="text-xs text-white/40 font-mono tracking-wider">
                tashkent@sabaliparfume.com
              </p>
            </div>
          </div>

          <!-- Working Hours -->
          <div class="flex flex-col space-y-4 pt-4 border-t border-white/5">
            <span class="text-xs uppercase tracking-[0.3em] text-white/40">{{ $t('contact.hours_title') }}</span>
            <div class="space-y-1 text-sm font-light text-white/60">
              <p class="flex justify-between max-w-xs">
                <span>{{ $t('contact.hours_week') }}</span>
                <span class="font-mono">24/7</span>
              </p>
              <p class="flex justify-between max-w-xs text-white/30">
                <span>{{ $t('contact.hours_sunday') }}</span>
                <span>{{ $t('contact.hours_sunday_val') }}</span>
              </p>
            </div>
          </div>

          <!-- Global Hotline -->
          <div class="flex flex-col space-y-2 pt-4 border-t border-white/5">
            <span class="text-xs uppercase tracking-[0.3em] text-white/40">{{ $t('contact.hotline_title') }}</span>
            <p class="text-lg font-light text-white tracking-wider font-mono">
              +998 (91) 410-13-13
            </p>
            <p class="text-xs text-white/30 font-light">
              {{ $t('contact.hotline_desc') }}
            </p>
          </div>

        </div> 
      </div>
    </section>

    

    <!-- Consultation Cards -->
    <section class="py-32 px-6 sm:px-12 md:px-24 bg-zinc-950 border-t border-white/5 relative">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-20">
          <h2 class="text-xs uppercase tracking-[0.4em] text-white/40 mb-4">
            {{ $t('contact.experience_title') }}
          </h2>
          <p class="text-2xl font-light tracking-wide text-white/80">
            {{ $t('contact.experience_sub') }}
          </p>
        </div>

        <div class="grid md:grid-cols-3 gap-12">
          
          <!-- Experience 1 -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <span class="text-[10px] font-mono tracking-widest text-white/30 uppercase">{{ $t('contact.exp1_num') }}</span>
            <h3 class="text-lg font-light tracking-widest text-white uppercase">
              {{ $t('contact.exp1_title') }}
            </h3>
            <p class="text-xs font-light text-white/50 leading-relaxed">
              {{ $t('contact.exp1_desc') }}
            </p>
          </div>

          <!-- Experience 2 -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <span class="text-[10px] font-mono tracking-widest text-white/30 uppercase">{{ $t('contact.exp2_num') }}</span>
            <h3 class="text-lg font-light tracking-widest text-white uppercase">
              {{ $t('contact.exp2_title') }}
            </h3>
            <p class="text-xs font-light text-white/50 leading-relaxed">
              {{ $t('contact.exp2_desc') }}
            </p>
          </div>

          <!-- Experience 3 -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <span class="text-[10px] font-mono tracking-widest text-white/30 uppercase">{{ $t('contact.exp3_num') }}</span>
            <h3 class="text-lg font-light tracking-widest text-white uppercase">
              {{ $t('contact.exp3_title') }}
            </h3>
            <p class="text-xs font-light text-white/50 leading-relaxed">
              {{ $t('contact.exp3_desc') }}
            </p>
          </div>

        </div>
      </div>
    </section>

  </div>
</template>

<script setup>
import { ref } from 'vue'
import bg from '~/assets/images/mobile-banner/13.jpg'
const isSubmitting = ref(false)
const submitStatus = ref(null)

const form = ref({
  name: '',
  email: '',
  subject: '',
  message: ''
})

const submitForm = () => {
  isSubmitting.value = true
  submitStatus.value = null

  // Simulate premium concierge API submit latency
  setTimeout(() => {
    isSubmitting.value = false
    submitStatus.value = 'success'
    
    // Reset form fields
    form.value = {
      name: '',
      email: '',
      subject: '',
      message: ''
    }
  }, 2000)
}
</script>

<style scoped>
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fadeIn 1.2s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}

/* Custom fade animations */
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>