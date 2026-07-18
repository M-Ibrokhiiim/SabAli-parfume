<template>
  <section class="py-12 bg-black">
    <!-- Grid container with slim responsive padding to maximize mobile width -->
    <div class="grid md:grid-cols-3 gap-10 max-w-7xl mx-auto px-4 sm:px-6 lg:px-10">
      <div 
        v-for="product in products" 
        :key="product.id" 
        class="group flex flex-col bg-zinc-950/40 border border-white/10 rounded-2xl p-4 mb-8 sm:mb-0 transition-all duration-500 hover:border-white/25 hover:bg-zinc-950/60"
      >
        <!-- Interactive Image Carousel (Luxurious portrait h-[360px] on mobile, compact h-[280px] on desktop) -->
        <div class="relative h-[360px] sm:h-[280px] w-full overflow-hidden rounded-xl select-none group">
          
          <!-- DESKTOP MODE: Original Absolute Stack with Elegant Cross-Fade -->
          <template v-if="isDesktop">
            <div 
              v-for="(img, idx) in product.images" 
              :key="`desktop-${idx}`"
              :class="[
                'absolute inset-0 w-full h-full transition-all duration-700 ease-in-out',
                product.currentImageIndex === idx ? 'opacity-100 z-10 scale-100' : 'opacity-0 z-0 scale-95 pointer-events-none'
              ]"
            >
              <img
                :src="img"
                class="h-full w-full object-cover transition-transform duration-1000 group-hover:scale-105"
                :alt="`${product.name} view ${idx + 1}`"
              />
            </div>
          </template>

          <!-- MOBILE MODE: Horizontal Swipe-Scroll Track with Snap Snapping -->
          <template v-else>
            <div 
              class="flex flex-row h-full w-full overflow-x-auto snap-x snap-mandatory scrollbar-none touch-pan-x"
              @scroll="handleScroll($event, product)"
            >
              <div 
                v-for="(img, idx) in product.images" 
                :key="`mobile-${idx}`"
                class="w-full h-full shrink-0 snap-center"
              >
                <img
                  :src="img"
                  class="h-full w-full object-cover"
                  :alt="`${product.name} view ${idx + 1}`"
                />
              </div>
            </div>
          </template>

          <!-- Shadow overlays on hover to increase navigation button contrast -->
          <div class="absolute inset-x-0 inset-y-0 bg-gradient-to-t from-black/60 via-transparent to-black/30 opacity-0 group-hover:opacity-100 transition-opacity duration-500 z-10 pointer-events-none"></div>

          <!-- Left (Previous) navigation button (Desktop Only) -->
          <button 
            v-if="isDesktop"
            @click.stop="prevImage(product)"
            class="hidden md:flex absolute left-4 top-1/2 -translate-y-1/2 z-20 items-center justify-center w-11 h-10 rounded-full bg-black/50 hover:bg-black/85 text-white/70 hover:text-white border border-white/10 backdrop-blur-md opacity-0 group-hover:opacity-100 transition-all duration-300 transform -translate-x-2 group-hover:translate-x-0"
            aria-label="Previous image"
          >
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
              <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
            </svg>
          </button>

          <!-- Right (Next) navigation button (Desktop Only) -->
          <button 
            v-if="isDesktop"
            @click.stop="nextImage(product)"
            class="hidden md:flex absolute right-4 top-1/2 -translate-y-1/2 z-20 items-center justify-center w-11 h-10 rounded-full bg-black/50 hover:bg-black/85 text-white/70 hover:text-white border border-white/10 backdrop-blur-md opacity-0 group-hover:opacity-100 transition-all duration-300 transform translate-x-2 group-hover:translate-x-0"
            aria-label="Next image"
          >
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
              <path stroke-linecap="round" stroke-linejoin="round" d="M8.25 4.5l7.5 7.5-7.5 7.5" />
            </svg>
          </button>

          <!-- Dynamic Pill-Shaped Slide Indicators -->
          <div class="absolute bottom-5 left-1/2 -translate-x-1/2 z-20 flex gap-2">
            <span 
              v-for="(img, idx) in product.images" 
              :key="`dot-${idx}`"
              :class="[
                'h-1.5 rounded-full transition-all duration-500 ease-out',
                product.currentImageIndex === idx ? 'bg-white w-5' : 'bg-white/30 w-1.5'
              ]"
            ></span>
          </div>
        </div>

        <!-- Product Details -->
        <div class="mt-6 flex flex-col flex-grow">
          <div class="flex items-baseline justify-between">
            <h3 class="text-xl font-light tracking-[0.15em] text-white">
              {{ product.name }}
            </h3>
            <span class="text-sm font-light tracking-wider text-white/80 border-b border-white/10 pb-0.5">
              {{ product.price }}
            </span>
          </div>
          <!-- Product description using dynamic i18n key -->
          <p class="mt-2 text-white/50 text-sm font-light leading-relaxed flex-grow">
            {{ $t(product.descKey) }}
          </p>

          <a 
            href="https://t.me/sabali013"
            target="_blank"
            class="mt-6 block w-full"
          >
            <button class="w-full py-3 bg-white text-black text-xs uppercase tracking-[0.25em] font-medium hover:bg-zinc-200 transition duration-300 select-none">
              {{ $t('products.purchase') }}
            </button>
          </a>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const isDesktop = ref(true)

const checkDevice = () => {
  if (typeof window !== 'undefined') {
    isDesktop.value = window.innerWidth >= 768 // 'md' breakpoint
  }
}

onMounted(() => {
  checkDevice()
  window.addEventListener('resize', checkDevice)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkDevice)
})

// Sync indicators/dots when swiping on mobile
const handleScroll = (event, product) => {
  if (isDesktop.value) return
  const scrollLeft = event.target.scrollLeft
  const width = event.target.clientWidth
  if (width > 0) {
    product.currentImageIndex = Math.round(scrollLeft / width)
  }
}

const products = ref([
  {
    id: 1,
    name: 'VELVET ROSE',
    descKey: 'products.velvet_rose',
    price: '$190',
    currentImageIndex: 0,
    images: [
      'https://images.unsplash.com/photo-1592945403244-b3fbafd7f539?q=80&w=800&auto=format&fit=crop',
      'https://images.unsplash.com/photo-1588405748373-122b2321bc31?q=80&w=800&auto=format&fit=crop'
    ]
  },
  {
    id: 2,
    name: 'JASMINE IMPÉRIAL',
    descKey: 'products.jasmine_imperial',
    price: '$210',
    currentImageIndex: 0,
    images: [
      'https://images.unsplash.com/photo-1616949755610-8c9bbc08f138?q=80&w=800&auto=format&fit=crop',
      'https://images.unsplash.com/photo-1541643600914-78b084683601?q=80&w=800&auto=format&fit=crop'
    ]
  },
  {
    id: 3,
    name: 'JASMINE IMPÉRIAL',
    descKey: 'products.jasmine_imperial',
    price: '$210',
    currentImageIndex: 0,
    images: [
      'https://i.pinimg.com/736x/ed/e9/13/ede9137faf4c0b6e31259a313110f552.jpg',
      'https://i.pinimg.com/736x/41/4f/9c/414f9c366edd0ec2b6a081617f4a3ca2.jpg'
    ]
  }
])

const nextImage = (product) => {
  product.currentImageIndex = (product.currentImageIndex + 1) % product.images.length
}

const prevImage = (product) => {
  product.currentImageIndex = (product.currentImageIndex - 1 + product.images.length) % product.images.length
}
</script>

<style scoped>
/* Hide scrollbar for Chrome, Safari and Opera */
.scrollbar-none::-webkit-scrollbar {
  display: none;
}

/* Hide scrollbar for IE, Edge and Firefox */
.scrollbar-none {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}
</style>