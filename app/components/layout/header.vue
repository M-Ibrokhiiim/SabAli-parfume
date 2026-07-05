<template>
  <header class="relative flex items-center bg-black justify-between px-6 sm:px-10 py-6 border-b border-white/10 z-40 select-none">
    <!-- Brand Logo -->
    <NuxtLink to="/" class="flex items-center">
      <h1 class="text-xl tracking-[6px] font-light text-white hover:text-white/80 transition-colors">SABALI</h1>
    </NuxtLink>

    <!-- Desktop Navigation (Hidden on Mobile) -->
    <nav class="hidden md:flex gap-10 text-xs uppercase tracking-[0.25em] font-medium text-white/60">
      <NuxtLink to="/" class="hover:text-white transition-colors duration-300">Bosh sahifa</NuxtLink>
      <NuxtLink to="/products" class="hover:text-white transition-colors duration-300">Mahsulotlar</NuxtLink>
      <NuxtLink to="/about" class="hover:text-white transition-colors duration-300">Haqida</NuxtLink>
      <NuxtLink to="/contact" class="hover:text-white transition-colors duration-300">Bog'lanish</NuxtLink>
    </nav>

    <!-- Mobile Menu Hamburger Button (Hidden on Desktop) -->
    <button 
      @click="isMobileMenuOpen = !isMobileMenuOpen"
      class="flex md:hidden flex-col justify-center items-center w-8 h-8 gap-1.5 text-white/80 hover:text-white focus:outline-none transition-colors duration-300 z-50"
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

    <!-- Custom Placeholder Button (Keep layout balance on desktop) -->
    <div class="hidden md:block w-16"></div>

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
            Bosh sahifa
          </NuxtLink>
          <NuxtLink 
            to="/#products" 
            @click="isMobileMenuOpen = false" 
            class="text-lg uppercase tracking-[0.3em] font-light text-white/70 hover:text-white transition-colors duration-300"
          >
            Mahsulotlar
          </NuxtLink>
          <NuxtLink 
            to="/about" 
            @click="isMobileMenuOpen = false" 
            class="text-lg uppercase tracking-[0.3em] font-light text-white/70 hover:text-white transition-colors duration-300"
          >
            Haqida
          </NuxtLink>
          <NuxtLink 
            to="/contact" 
            @click="isMobileMenuOpen = false" 
            class="text-lg uppercase tracking-[0.3em] font-light text-white/70 hover:text-white transition-colors duration-300"
          >
            Bog'lanish
          </NuxtLink>
        </nav>
      </div>
    </transition>
  </header>
</template>

<script setup>
import { ref } from 'vue'

const isMobileMenuOpen = ref(false)
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
