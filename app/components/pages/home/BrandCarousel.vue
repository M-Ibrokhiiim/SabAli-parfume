<template>
  <section 
     class="py-16  cursor-pointer mt-[1px] bg-black overflow-hidden">
    <!-- Marquee Container -->
    <div class="marquee-container relative w-full overflow-hidden py-4 select-none">
      <!-- Luxurious gradient shadow fade overlays on the sides -->
      <div class="pointer-events-none absolute inset-y-0 left-0 w-20 sm:w-32 md:w-48 bg-gradient-to-r from-black via-black/80 to-transparent z-10"></div>
      <div class="pointer-events-none absolute inset-y-0 right-0 w-20 sm:w-32 md:w-48 bg-gradient-to-l from-black via-black/80 to-transparent z-10"></div>

      <!-- Marquee Tracks -->
      <div @click="navigateTo('/products')" class="flex flex-row flex-nowrap w-full overflow-hidden">
        <!-- First Track -->
        <div class="marquee-track flex flex-row flex-nowrap shrink-0 items-center animate-marquee">
          <div 
            v-for="(brand, index) in brands" 
            :key="`track1-${index}`" 
            class="brand-item group flex items-center gap-6 px-8 sm:px-12 md:px-16 lg:px-20 cursor-pointer"
          >
            <!-- SVG Brand Logo -->
            <div class="h-11 sm:h-14 md:h-16 w-auto flex items-center justify-center text-white/30 group-hover:text-white transition-colors duration-300">
              <!-- Chanel -->
              <svg 
                v-if="brand.id === 'chanel'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto" 
                fill="currentColor"
              >
                <path fill-rule="evenodd" d="M 32.5,50 C 32.5,40.3 40.3,32.5 50,32.5 C 56.2,32.5 61.7,35.7 64.9,40.6 L 73.1,34.4 C 67.7,27.2 59.4,22.5 50,22.5 C 34.8,22.5 22.5,34.8 22.5,50 C 22.5,65.2 34.8,77.5 50,77.5 C 59.4,77.5 67.7,72.8 73.1,65.6 L 64.9,59.4 C 61.7,64.3 56.2,67.5 50,67.5 C 40.3,67.5 32.5,59.7 32.5,50 Z M 67.5,50 C 67.5,59.7 59.7,67.5 50,67.5 C 43.8,67.5 38.3,64.3 35.1,59.4 L 26.9,65.6 C 32.3,72.8 40.6,77.5 50,77.5 C 65.2,77.5 77.5,65.2 77.5,50 C 77.5,34.8 65.2,22.5 50,22.5 C 40.6,22.5 32.3,27.2 26.9,34.4 L 35.1,40.6 C 38.3,35.7 43.8,32.5 50,32.5 C 59.7,32.5 67.5,40.3 67.5,50 Z" />
              </svg>

              <!-- Gucci -->
              <svg 
                v-else-if="brand.id === 'gucci'" 
                viewBox="0 0 512 512" 
                class="h-[85%] w-auto" 
                fill="currentColor"
              >
                <path d="M 210 140 C 130 140, 110 200, 110 256 C 110 312, 130 372, 210 372 C 270 372, 290 330, 295 300 L 230 300 L 230 270 L 330 270 C 330 360, 270 412, 210 412 C 110 412, 70 330, 70 256 C 70 182, 110 100, 210 100 C 270 100, 325 145, 330 210 L 290 210 C 285 170, 260 140, 210 140 Z" />
                <path d="M 302 372 C 382 372, 402 312, 402 256 C 402 200, 382 140, 302 140 C 242 140, 222 182, 217 212 L 282 212 L 282 242 L 182 242 C 182 152, 242 100, 302 100 C 402 100, 442 182, 442 256 C 442 330, 402 412, 302 412 C 242 412, 187 367, 182 302 L 222 302 C 227 342, 252 372, 302 372 Z" />
              </svg>

              <!-- Versace -->
              <svg 
                v-else-if="brand.id === 'versace'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto text-white/30 group-hover:text-[#D4AF37] transition-colors duration-300" 
                fill="none" 
                stroke="currentColor" 
                stroke-width="2.5"
              >
                <circle cx="50" cy="50" r="45" />
                <circle cx="50" cy="50" r="39" stroke-width="1.5" stroke-dasharray="3, 2" />
                <path d="M 38 36 L 50 66 L 62 36" stroke-width="3" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M 32 36 H 44 M 56 36 H 68" stroke-width="2" stroke-linecap="round" />
              </svg>

              <!-- Dior -->
              <svg 
                v-else-if="brand.id === 'dior'" 
                viewBox="0 0 200 120" 
                class="h-full w-auto" 
                fill="currentColor" 
                fill-rule="evenodd"
              >
                <path d="M 85 15 L 125 15 A 45 45 0 0 1 125 105 L 85 105 Z M 97 27 L 123 27 A 33 33 0 0 1 123 93 L 97 93 Z" />
                <path d="M 105 35 A 25 25 0 0 0 65 60 A 25 25 0 0 0 105 85 L 105 73 A 13 13 0 0 1 77 60 A 13 13 0 0 1 105 47 Z" />
              </svg>

              <!-- Tom Ford -->
              <svg 
                v-else-if="brand.id === 'tomford'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto" 
                fill="currentColor"
              >
                <path d="M 25 25 H 75 V 35 H 55 V 75 H 45 V 35 H 25 Z" />
                <path d="M 50 45 H 80 V 55 H 60 V 62 H 75 V 72 H 60 V 75 H 50 Z" />
              </svg>

              <!-- YSL -->
              <svg 
                v-else-if="brand.id === 'yves-saint-laurent'" 
                viewBox="0 0 100 160" 
                class="h-[105%] w-auto" 
                fill="currentColor" 
                fill-rule="evenodd"
              >
                <path d="M 38,10 C 38,10 34,25 28,35 C 22,45 12,55 5,60 C 10,62 18,58 24,50 C 30,42 35,30 38,22 L 38,85 C 38,95 35,105 30,112 C 35,110 39,102 41,92 L 41,22 C 44,30 49,42 55,50 C 61,58 69,62 74,60 C 67,55 57,45 51,35 C 45,25 41,10 41,10 Z" />
                <path d="M 48,35 C 40,35 30,40 25,48 C 20,56 22,65 28,70 C 35,75 55,78 60,85 C 65,92 62,102 52,108 C 42,114 30,112 22,105 C 28,108 38,108 45,104 C 52,100 54,92 50,86 C 46,80 30,76 24,70 C 18,64 18,52 28,44 C 38,36 50,38 58,42 C 54,38 48,35 48,35 Z" />
                <path d="M 46,65 L 46,125 C 46,132 50,136 58,138 C 50,138 44,134 42,128 L 42,75 C 42,75 38,80 32,85 C 36,82 40,76 42,72 L 42,65 Z M 25,125 C 35,125 55,128 65,135 C 55,133 35,133 25,135 Z" />
              </svg>

              <!-- Prada -->
              <svg 
                v-else-if="brand.id === 'prada'" 
                viewBox="0 0 500 300" 
                class="h-[85%] w-auto" 
                fill="currentColor"
              >
                <path d="M 10 20 L 490 20 L 250 285 Z" fill="none" stroke="currentColor" stroke-width="12" stroke-linejoin="round" />
                <path d="M 35 35 L 465 35 L 250 265 Z" />
              </svg>

              <!-- Hermès -->
              <svg 
                v-else-if="brand.id === 'hermes'" 
                viewBox="0 0 120 120" 
                class="h-full w-auto" 
                fill="none" 
                stroke="currentColor" 
                stroke-width="2.5"
              >
                <circle cx="60" cy="60" r="54" />
                <path d="M 35 30 H 55 V 38 H 48 V 56 H 72 V 38 H 65 V 30 H 85 V 38 H 79 V 82 H 85 V 90 H 65 V 82 H 72 V 64 H 48 V 82 H 55 V 90 H 35 V 82 H 41 V 38 H 35 Z" fill="currentColor" />
              </svg>

              <!-- Givenchy -->
              <svg 
                v-else-if="brand.id === 'givenchy'" 
                viewBox="0 0 500 510" 
                class="h-full w-auto" 
                fill="currentColor"
              >
                <path d="M 80 80 L 230 80 L 230 120 L 130 120 L 130 180 L 230 180 L 230 230 L 80 230 L 80 80 Z M 130 150 L 180 150 L 180 120 L 130 120 Z" />
                <path d="M 420 80 L 270 80 L 270 120 L 370 120 L 370 180 L 270 180 L 270 230 L 420 230 L 420 80 Z M 370 150 L 320 150 L 320 120 L 370 120 Z" />
                <path d="M 80 430 L 230 430 L 230 390 L 130 390 L 130 330 L 230 330 L 230 280 L 80 280 L 80 430 Z M 130 360 L 180 360 L 180 390 L 130 390 Z" />
                <path d="M 420 430 L 270 430 L 270 390 L 370 390 L 370 330 L 270 330 L 270 280 L 420 280 L 420 430 Z M 370 360 L 320 360 L 320 390 L 370 390 Z" />
              </svg>

              <!-- Creed -->
              <svg 
                v-else-if="brand.id === 'creed'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto" 
                fill="none" 
                stroke="currentColor" 
                stroke-width="2.5" 
                stroke-linejoin="round"
              >
                <path d="M 20 70 L 15 40 L 35 55 L 50 30 L 65 55 L 85 40 L 80 70 Z" fill="currentColor" fill-opacity="0.1" />
                <path d="M 20 70 H 80 V 76 H 20 Z" fill="currentColor" />
                <circle cx="15" cy="40" r="3.5" fill="currentColor" />
                <circle cx="35" cy="55" r="3.5" fill="currentColor" />
                <circle cx="50" cy="30" r="3.5" fill="currentColor" />
                <circle cx="65" cy="55" r="3.5" fill="currentColor" />
                <circle cx="85" cy="40" r="3.5" fill="currentColor" />
                <path d="M 50 45 V 60 M 42 52 H 58" stroke-width="2" />
              </svg>
            </div>

            <!-- Brand Name -->
            <span 
              :class="[
                'text-white/30 group-hover:text-white transition-colors duration-300 whitespace-nowrap',
                brand.fontClass
              ]"
            >
              {{ brand.name }}
            </span>
          </div>
        </div>

        <!-- Second Track (Identical clone for perfect looping) -->
        <div class="marquee-track flex flex-row flex-nowrap shrink-0 items-center animate-marquee" aria-hidden="true">
          <div 
            v-for="(brand, index) in brands" 
            :key="`track2-${index}`" 
            class="brand-item group flex items-center gap-6 px-8 sm:px-12 md:px-16 lg:px-20 cursor-pointer"
          >
            <!-- SVG Brand Logo -->
            <div class="h-11 sm:h-14 md:h-16 w-auto flex items-center justify-center text-white/30 group-hover:text-white transition-colors duration-300">
              <!-- Chanel -->
              <svg 
                v-if="brand.id === 'chanel'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto" 
                fill="currentColor"
              >
                <path fill-rule="evenodd" d="M 32.5,50 C 32.5,40.3 40.3,32.5 50,32.5 C 56.2,32.5 61.7,35.7 64.9,40.6 L 73.1,34.4 C 67.7,27.2 59.4,22.5 50,22.5 C 34.8,22.5 22.5,34.8 22.5,50 C 22.5,65.2 34.8,77.5 50,77.5 C 59.4,77.5 67.7,72.8 73.1,65.6 L 64.9,59.4 C 61.7,64.3 56.2,67.5 50,67.5 C 40.3,67.5 32.5,59.7 32.5,50 Z M 67.5,50 C 67.5,59.7 59.7,67.5 50,67.5 C 43.8,67.5 38.3,64.3 35.1,59.4 L 26.9,65.6 C 32.3,72.8 40.6,77.5 50,77.5 C 65.2,77.5 77.5,65.2 77.5,50 C 77.5,34.8 65.2,22.5 50,22.5 C 40.6,22.5 32.3,27.2 26.9,34.4 L 35.1,40.6 C 38.3,35.7 43.8,32.5 50,32.5 C 59.7,32.5 67.5,40.3 67.5,50 Z" />
              </svg>

              <!-- Gucci -->
              <svg 
                v-else-if="brand.id === 'gucci'" 
                viewBox="0 0 512 512" 
                class="h-[85%] w-auto" 
                fill="currentColor"
              >
                <path d="M 210 140 C 130 140, 110 200, 110 256 C 110 312, 130 372, 210 372 C 270 372, 290 330, 295 300 L 230 300 L 230 270 L 330 270 C 330 360, 270 412, 210 412 C 110 412, 70 330, 70 256 C 70 182, 110 100, 210 100 C 270 100, 325 145, 330 210 L 290 210 C 285 170, 260 140, 210 140 Z" />
                <path d="M 302 372 C 382 372, 402 312, 402 256 C 402 200, 382 140, 302 140 C 242 140, 222 182, 217 212 L 282 212 L 282 242 L 182 242 C 182 152, 242 100, 302 100 C 402 100, 442 182, 442 256 C 442 330, 402 412, 302 412 C 242 412, 187 367, 182 302 L 222 302 C 227 342, 252 372, 302 372 Z" />
              </svg>

              <!-- Versace -->
              <svg 
                v-else-if="brand.id === 'versace'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto text-white/30 group-hover:text-[#D4AF37] transition-colors duration-300" 
                fill="none" 
                stroke="currentColor" 
                stroke-width="2.5"
              >
                <circle cx="50" cy="50" r="45" />
                <circle cx="50" cy="50" r="39" stroke-width="1.5" stroke-dasharray="3, 2" />
                <path d="M 38 36 L 50 66 L 62 36" stroke-width="3" stroke-linecap="round" stroke-linejoin="round" />
                <path d="M 32 36 H 44 M 56 36 H 68" stroke-width="2" stroke-linecap="round" />
              </svg>

              <!-- Dior -->
              <svg 
                v-else-if="brand.id === 'dior'" 
                viewBox="0 0 200 120" 
                class="h-full w-auto" 
                fill="currentColor" 
                fill-rule="evenodd"
              >
                <path d="M 85 15 L 125 15 A 45 45 0 0 1 125 105 L 85 105 Z M 97 27 L 123 27 A 33 33 0 0 1 123 93 L 97 93 Z" />
                <path d="M 105 35 A 25 25 0 0 0 65 60 A 25 25 0 0 0 105 85 L 105 73 A 13 13 0 0 1 77 60 A 13 13 0 0 1 105 47 Z" />
              </svg>

              <!-- Tom Ford -->
              <svg 
                v-else-if="brand.id === 'tomford'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto" 
                fill="currentColor"
              >
                <path d="M 25 25 H 75 V 35 H 55 V 75 H 45 V 35 H 25 Z" />
                <path d="M 50 45 H 80 V 55 H 60 V 62 H 75 V 72 H 60 V 75 H 50 Z" />
              </svg>

              <!-- YSL -->
              <svg 
                v-else-if="brand.id === 'yves-saint-laurent'" 
                viewBox="0 0 100 160" 
                class="h-[105%] w-auto" 
                fill="currentColor" 
                fill-rule="evenodd"
              >
                <path d="M 38,10 C 38,10 34,25 28,35 C 22,45 12,55 5,60 C 10,62 18,58 24,50 C 30,42 35,30 38,22 L 38,85 C 38,95 35,105 30,112 C 35,110 39,102 41,92 L 41,22 C 44,30 49,42 55,50 C 61,58 69,62 74,60 C 67,55 57,45 51,35 C 45,25 41,10 41,10 Z" />
                <path d="M 48,35 C 40,35 30,40 25,48 C 20,56 22,65 28,70 C 35,75 55,78 60,85 C 65,92 62,102 52,108 C 42,114 30,112 22,105 C 28,108 38,108 45,104 C 52,100 54,92 50,86 C 46,80 30,76 24,70 C 18,64 18,52 28,44 C 38,36 50,38 58,42 C 54,38 48,35 48,35 Z" />
                <path d="M 46,65 L 46,125 C 46,132 50,136 58,138 C 50,138 44,134 42,128 L 42,75 C 42,75 38,80 32,85 C 36,82 40,76 42,72 L 42,65 Z M 25,125 C 35,125 55,128 65,135 C 55,133 35,133 25,135 Z" />
              </svg>

              <!-- Prada -->
              <svg 
                v-else-if="brand.id === 'prada'" 
                viewBox="0 0 500 300" 
                class="h-[85%] w-auto" 
                fill="currentColor"
              >
                <path d="M 10 20 L 490 20 L 250 285 Z" fill="none" stroke="currentColor" stroke-width="12" stroke-linejoin="round" />
                <path d="M 35 35 L 465 35 L 250 265 Z" />
              </svg>

              <!-- Hermès -->
              <svg 
                v-else-if="brand.id === 'hermes'" 
                viewBox="0 0 120 120" 
                class="h-full w-auto" 
                fill="none" 
                stroke="currentColor" 
                stroke-width="2.5"
              >
                <circle cx="60" cy="60" r="54" />
                <path d="M 35 30 H 55 V 38 H 48 V 56 H 72 V 38 H 65 V 30 H 85 V 38 H 79 V 82 H 85 V 90 H 65 V 82 H 72 V 64 H 48 V 82 H 55 V 90 H 35 V 82 H 41 V 38 H 35 Z" fill="currentColor" />
              </svg>

              <!-- Givenchy -->
              <svg 
                v-else-if="brand.id === 'givenchy'" 
                viewBox="0 0 500 510" 
                class="h-full w-auto" 
                fill="currentColor"
              >
                <path d="M 80 80 L 230 80 L 230 120 L 130 120 L 130 180 L 230 180 L 230 230 L 80 230 L 80 80 Z M 130 150 L 180 150 L 180 120 L 130 120 Z" />
                <path d="M 420 80 L 270 80 L 270 120 L 370 120 L 370 180 L 270 180 L 270 230 L 420 230 L 420 80 Z M 370 150 L 320 150 L 320 120 L 370 120 Z" />
                <path d="M 80 430 L 230 430 L 230 390 L 130 390 L 130 330 L 230 330 L 230 280 L 80 280 L 80 430 Z M 130 360 L 180 360 L 180 390 L 130 390 Z" />
                <path d="M 420 430 L 270 430 L 270 390 L 370 390 L 370 330 L 270 330 L 270 280 L 420 280 L 420 430 Z M 370 360 L 320 360 L 320 390 L 370 390 Z" />
              </svg>

              <!-- Creed -->
              <svg 
                v-else-if="brand.id === 'creed'" 
                viewBox="0 0 100 100" 
                class="h-full w-auto" 
                fill="none" 
                stroke="currentColor" 
                stroke-width="2.5" 
                stroke-linejoin="round"
              >
                <path d="M 20 70 L 15 40 L 35 55 L 50 30 L 65 55 L 85 40 L 80 70 Z" fill="currentColor" fill-opacity="0.1" />
                <path d="M 20 70 H 80 V 76 H 20 Z" fill="currentColor" />
                <circle cx="15" cy="40" r="3.5" fill="currentColor" />
                <circle cx="35" cy="55" r="3.5" fill="currentColor" />
                <circle cx="50" cy="30" r="3.5" fill="currentColor" />
                <circle cx="65" cy="55" r="3.5" fill="currentColor" />
                <circle cx="85" cy="40" r="3.5" fill="currentColor" />
                <path d="M 50 45 V 60 M 42 52 H 58" stroke-width="2" />
              </svg>
            </div>

            <!-- Brand Name -->
            <span 
              :class="[
                'text-white/30 group-hover:text-white transition-colors duration-300 whitespace-nowrap',
                brand.fontClass
              ]"
            >
              {{ brand.name }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { computed } from 'vue';
const brands = [
  { 
    id: 'chanel',
    name: 'CHANEL', 
    fontClass: 'font-sans font-black tracking-[0.35em] text-2xl sm:text-3xl' 
  },
  { 
    id: 'gucci',
    name: 'GUCCI', 
    fontClass: 'font-serif font-semibold tracking-[0.3em] text-2xl sm:text-3xl' 
  },
  { 
    id: 'versace',
    name: 'VERSACE', 
    fontClass: 'font-sans font-light tracking-[0.3em] text-xl sm:text-2xl' 
  },
  { 
    id: 'dior',
    name: 'Dior', 
    fontClass: 'font-serif italic font-bold tracking-[0.15em] text-3xl sm:text-4xl' 
  },
  { 
    id: 'tomford',
    name: 'TOM FORD', 
    fontClass: 'font-sans font-extrabold tracking-[0.2em] text-xl sm:text-2xl' 
  },
  { 
    id: 'yves-saint-laurent',
    name: 'YVES SAINT LAURENT', 
    fontClass: 'font-serif font-light tracking-[0.25em] text-lg sm:text-xl' 
  },
  { 
    id: 'prada',
    name: 'PRADA', 
    fontClass: 'font-serif font-extrabold tracking-[0.3em] text-xl sm:text-2xl' 
  },
  { 
    id: 'hermes',
    name: 'HERMÈS', 
    fontClass: 'font-mono font-bold tracking-[0.25em] text-xl sm:text-2xl' 
  },
  { 
    id: 'givenchy',
    name: 'GIVENCHY', 
    fontClass: 'font-sans font-medium tracking-[0.3em] text-xl sm:text-2xl' 
  },
  { 
    id: 'creed',
    name: 'CREED', 
    fontClass: 'font-serif font-black tracking-[0.2em] text-2xl sm:text-3xl' 
  }
]

const props = defineProps({
  isMobile: Boolean
})

const duration = computed(() => props.isMobile ? '40s' : '50s')
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
  animation: marquee v-bind(duration) linear infinite;
}
</style>
