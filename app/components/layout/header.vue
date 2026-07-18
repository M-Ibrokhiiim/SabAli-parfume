<template>
  <header class="relative flex items-center bg-black justify-between px-6 sm:px-10 py-6 border-b border-white/10 z-40 select-none">
    <!-- Brand Logo -->
    <NuxtLink to="/" class="flex items-center">
      <h1 class="text-xl tracking-[6px] font-light text-white hover:text-white/80 transition-colors">SABALI</h1>
    </NuxtLink>

    <!-- Desktop Navigation (Hidden on Mobile) -->
    <nav class="hidden md:flex gap-10 text-xs uppercase tracking-[0.25em] font-medium text-white/60">
      <NuxtLink to="/" class="hover:text-white transition-colors duration-300">{{ $t('nav.home') }}</NuxtLink>
      <NuxtLink to="/products" class="hover:text-white transition-colors duration-300">{{ $t('nav.products') }}</NuxtLink>
      <NuxtLink to="/about" class="hover:text-white transition-colors duration-300">{{ $t('nav.about') }}</NuxtLink>
      <NuxtLink to="/contact" class="hover:text-white transition-colors duration-300">{{ $t('nav.contact') }}</NuxtLink>
    </nav>

    <!-- Right Side Actions (Language toggle and mobile menu) -->
    <div class="flex items-center gap-4 z-50">
      <!-- Globe Language Toggle (Black background, white globe) -->
      <button 
        @click="toggleLanguage"
        class="flex items-center gap-1.5 px-3 py-1.5 rounded-full bg-black hover:bg-zinc-900 border border-white/10 text-white/80 hover:text-white transition-all duration-300"
        :aria-label="`Switch to ${locale === 'uz' ? 'Russian' : 'Uzbek'}`"
      >
        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-4.5 h-4.5 text-white">
          <path stroke-linecap="round" stroke-linejoin="round" d="M12 21a9.004 9.004 0 008.716-6.747M12 21a9.004 9.004 0 01-8.716-6.747M12 21c2.485 0 4.5-4.03 4.5-9S14.485 3 12 3m0 18c-2.485 0-4.5-4.03-4.5-9S9.515 3 12 3m0 0a8.997 8.997 0 017.843 4.582M12 3a8.997 8.997 0 00-7.843 4.582" />
        </svg>
        <span class="text-[10px] font-mono font-medium uppercase tracking-wider text-white/90">{{ locale }}</span>
      </button>

      <!-- Mobile Menu Hamburger Button (Hidden on Desktop) -->
      <button 
        @click="isMobileMenuOpen = !isMobileMenuOpen"
        class="flex md:hidden flex-col justify-center items-center w-8 h-8 gap-1.5 text-white/80 hover:text-white focus:outline-none transition-colors duration-300"
        :aria-label="isMobileMenuOpen ? 'Close navigation menu' : 'Open navigation menu'"
      >
        <span 
          class="w-6 h-[1px] bg-white transition-transform duration-300 ease-out"
          :class="isMobileMenuOpen ? 'translate-y-[7px] rotate-45' : ''"
        ></span>
        <span 
          class="w-6 h-[1px] bg-white transition-opacity duration-300 ease-out"
          :class="isMobileMenuOpen ? 'opacity-0' : 'opacity-100'"
        ></span>
        <span 
          class="w-6 h-[1px] bg-white transition-transform duration-300 ease-out"
          :class="isMobileMenuOpen ? '-translate-y-[7px] -rotate-45' : ''"
        ></span>
      </button>
    </div>

    <!-- Full-Screen Mobile Drawer Overlay -->
    <transition name="mobile-menu-fade">
      <div 
        v-if="isMobileMenuOpen" 
        class="fixed inset-0 bg-black/98 backdrop-blur-lg z-40 flex items-center justify-center flex-col md:hidden"
      >
        <nav class="flex flex-col items-center space-y-10 text-center select-none">
          <NuxtLink 
            to="/" 
            @click="isMobileMenuOpen = false" 
            class="text-lg uppercase tracking-[0.3em] font-light text-white/70 hover:text-white transition-colors duration-300"
          >
            {{ $t('nav.home') }}
          </NuxtLink>
          <NuxtLink 
            to="/products" 
            @click="isMobileMenuOpen = false" 
            class="text-lg uppercase tracking-[0.3em] font-light text-white/70 hover:text-white transition-colors duration-300"
          >
            {{ $t('nav.products') }}
          </NuxtLink>
          <NuxtLink 
            to="/about" 
            @click="isMobileMenuOpen = false" 
            class="text-lg uppercase tracking-[0.3em] font-light text-white/70 hover:text-white transition-colors duration-300"
          >
            {{ $t('nav.about') }}
          </NuxtLink>
          <NuxtLink 
            to="/contact" 
            @click="isMobileMenuOpen = false" 
            class="text-lg uppercase tracking-[0.3em] font-light text-white/70 hover:text-white transition-colors duration-300"
          >
            {{ $t('nav.contact') }}
          </NuxtLink>
        </nav>
      </div>
    </transition>
  </header>
</template>

<script setup>
import { ref } from 'vue'
import { useI18n } from 'vue-i18n'

const isMobileMenuOpen = ref(false)
const { locale, setLocale } = useI18n()

const toggleLanguage = () => {
  setLocale(locale.value === 'uz' ? 'ru' : 'uz')
}
</script>

<style scoped>
/* Mobile Drawer Fade & Scale Transition */
.mobile-menu-fade-enter-active,
.mobile-menu-fade-leave-active {
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.mobile-menu-fade-enter-from {
  opacity: 0;
  transform: scale(0.95);
}

.mobile-menu-fade-leave-to {
  opacity: 0;
  transform: scale(0.95);
}
</style>
