<template>
  <section class="py-16 border-t border-white/10 bg-black overflow-hidden">
    <!-- Section Title -->
    <div class="px-10 mb-10 text-center">
      <h2 class="text-xs uppercase tracking-[0.4em] text-white/40 font-light">
        Featured Luxury Houses
      </h2>
    </div>

    <!-- Marquee Container -->
    <div class="marquee-container relative w-full overflow-hidden py-4 select-none">
      <!-- Luxurious gradient shadow fade overlays on the sides -->
      <div class="pointer-events-none absolute inset-y-0 left-0 w-20 sm:w-32 md:w-48 bg-gradient-to-r from-black via-black/80 to-transparent z-10"></div>
      <div class="pointer-events-none absolute inset-y-0 right-0 w-20 sm:w-32 md:w-48 bg-gradient-to-l from-black via-black/80 to-transparent z-10"></div>

      <!-- Marquee Tracks -->
      <div class="flex flex-row flex-nowrap w-full overflow-hidden">
        <!-- First Track -->
        <div class="marquee-track flex flex-row flex-nowrap shrink-0 items-center animate-marquee">
          <div 
            v-for="(brand, index) in brands" 
            :key="`track1-${index}`" 
            class="brand-item flex items-center justify-center px-12 sm:px-16 md:px-20"
          >
            <!-- SVG / Rendered Brand Logo -->
            <div class="h-8 flex items-center justify-center transition-all duration-300 transform hover:scale-110">
              <!-- Render text logo with specialized high-luxury typography styling -->
              <span 
                :class="[
                  'text-white/40 hover:text-white transition-colors duration-300 tracking-[0.25em] whitespace-nowrap cursor-pointer',
                  brand.fontClass
                ]"
              >
                {{ brand.name }}
              </span>
            </div>
          </div>
        </div>

        <!-- Second Track (Identical clone for perfect looping) -->
        <div class="marquee-track flex flex-row flex-nowrap shrink-0 items-center animate-marquee" aria-hidden="true">
          <div 
            v-for="(brand, index) in brands" 
            :key="`track2-${index}`" 
            class="brand-item flex items-center justify-center px-12 sm:px-16 md:px-20"
          >
            <!-- SVG / Rendered Brand Logo -->
            <div class="h-8 flex items-center justify-center transition-all duration-300 transform hover:scale-110">
              <span 
                :class="[
                  'text-white/40 hover:text-white transition-colors duration-300 tracking-[0.25em] whitespace-nowrap cursor-pointer',
                  brand.fontClass
                ]"
              >
                {{ brand.name }}
              </span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
const brands = [
  { 
    name: 'CHANEL', 
    fontClass: 'font-sans font-black tracking-[0.35em] text-lg sm:text-xl' 
  },
  { 
    name: 'GUCCI', 
    fontClass: 'font-serif font-semibold tracking-[0.3em] text-lg sm:text-xl' 
  },
  { 
    name: 'VERSACE', 
    fontClass: 'font-sans font-light tracking-[0.3em] text-base sm:text-lg' 
  },
  { 
    name: 'Dior', 
    fontClass: 'font-serif italic font-bold tracking-[0.15em] text-xl sm:text-2xl' 
  },
  { 
    name: 'TOM FORD', 
    fontClass: 'font-sans font-extrabold tracking-[0.2em] text-base sm:text-lg' 
  },
  { 
    name: 'YVES SAINT LAURENT', 
    fontClass: 'font-serif font-light tracking-[0.25em] text-sm sm:text-base' 
  },
  { 
    name: 'PRADA', 
    fontClass: 'font-serif font-extrabold tracking-[0.3em] text-base sm:text-lg' 
  },
  { 
    name: 'HERMÈS', 
    fontClass: 'font-mono font-bold tracking-[0.25em] text-base sm:text-lg' 
  },
  { 
    name: 'GIVENCHY', 
    fontClass: 'font-sans font-medium tracking-[0.3em] text-base sm:text-lg' 
  },
  { 
    name: 'CREED', 
    fontClass: 'font-serif font-black tracking-[0.2em] text-lg sm:text-xl' 
  }
]
</script>

<style scoped>
@keyframes marquee {
  0% {
    transform: translateX(0%);
  }
  100% {
    transform: translateX(-100%);
  }
}

.animate-marquee {
  animation: marquee 45s linear infinite;
}

/* Pause the animation when container is hovered */
.marquee-container:hover .animate-marquee {
  animation-play-state: paused;
}
</style>
