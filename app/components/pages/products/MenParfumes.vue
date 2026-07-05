<template>
  <section class="py-12 bg-black">
    <div class="grid md:grid-cols-3 lg:grid-cols-3 gap-12 max-w-8xl mx-auto px-6">
      <div 
        v-for="product in products" 
        :key="product.id" 
        class="group flex flex-col bg-zinc-950/40 border border-white/5 rounded-2xl p-4 transition-all duration-500 hover:border-white/10 hover:bg-zinc-950/60"
      >
        <!-- Interactive Image Carousel -->
        <div class="relative h-[450px] w-full overflow-hidden rounded-xl select-none group">
          
          <!-- Product Images with elegant cross-fade transition -->
          <div 
            v-for="(img, idx) in product.images" 
            :key="idx"
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

          <!-- Shadow overlays on hover to increase navigation button contrast -->
          <div class="absolute inset-x-0 inset-y-0 bg-gradient-to-t from-black/60 via-transparent to-black/30 opacity-0 group-hover:opacity-100 transition-opacity duration-500 z-10 pointer-events-none"></div>

          <!-- Left (Previous) navigation button -->
          <button 
            @click.stop="prevImage(product)"
            class="absolute left-4 top-1/2 -translate-y-1/2 z-20 flex items-center justify-center w-11 h-10 rounded-full bg-black/50 hover:bg-black/85 text-white/70 hover:text-white border border-white/10 backdrop-blur-md opacity-0 group-hover:opacity-100 transition-all duration-300 transform -translate-x-2 group-hover:translate-x-0"
            aria-label="Previous image"
          >
            <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="2" stroke="currentColor" class="w-5 h-5">
              <path stroke-linecap="round" stroke-linejoin="round" d="M15.75 19.5L8.25 12l7.5-7.5" />
            </svg>
          </button>

          <!-- Right (Next) navigation button -->
          <button 
            @click.stop="nextImage(product)"
            class="absolute right-4 top-1/2 -translate-y-1/2 z-20 flex items-center justify-center w-11 h-10 rounded-full bg-black/50 hover:bg-black/85 text-white/70 hover:text-white border border-white/10 backdrop-blur-md opacity-0 group-hover:opacity-100 transition-all duration-300 transform translate-x-2 group-hover:translate-x-0"
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
                product.currentImageIndex === idx ? 'bg-white w-5' : 'bg-white/30 w-1.5 hover:bg-white/50'
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
          <p class="mt-2 text-white/50 text-sm font-light leading-relaxed">
            {{ product.description }}
          </p>

        <a 
           href="https://t.me/sabali013"
           target="_blank"
           >
          <button class="mt-6 w-full py-3 bg-white text-black text-xs uppercase tracking-[0.25em] font-medium hover:bg-zinc-200 transition duration-300 select-none">
             Xarid
          </button>
        </a>  
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref } from 'vue'

const products = ref([
  {
    id: 1,
    name: 'MIDNIGHT OUD',
    description: 'A deep, mysterious blend of precious agarwood, warm amber resins, and smoky incense. Designed for the elegant and bold modern gentleman.',
    price: '$185',
    currentImageIndex: 0,
    images: [
      'https://images.unsplash.com/photo-1615634260167-c8cdede054de?q=80&w=800&auto=format&fit=crop',
      'https://images.unsplash.com/photo-1547887537-6158d64c35b3?q=80&w=800&auto=format&fit=crop'
    ]
  },
  {
    id: 2,
    name: 'AMBER NOIR',
    description: 'A warm, bold fusion of dark patchouli, creamy Madagascar vanilla, and spicy black pepper. Exudes absolute luxury and sophisticated masculine charm.',
    price: '$195',
    currentImageIndex: 0,
    images: [
      'https://images.unsplash.com/photo-1594035910387-fea47794261f?q=80&w=800&auto=format&fit=crop',
      'https://images.unsplash.com/photo-1523293182086-7651a899d37f?q=80&w=800&auto=format&fit=crop'
    ]
  },
  {
    id: 3,
    name: 'AMBER NOIR',
    description: 'A warm, bold fusion of dark patchouli, creamy Madagascar vanilla, and spicy black pepper. Exudes absolute luxury and sophisticated masculine charm.',
    price: '$195',
    currentImageIndex: 0,
    images: [
      'https://images.unsplash.com/photo-1594035910387-fea47794261f?q=80&w=800&auto=format&fit=crop',
      'https://images.unsplash.com/photo-1523293182086-7651a899d37f?q=80&w=800&auto=format&fit=crop'
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
