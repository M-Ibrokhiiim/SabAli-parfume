<template>
  <div class="bg-black text-white">
    <!-- HERO -->
    <section :class="[
      'flex items-center justify-center relative overflow-hidden',
      isMobile ? 'h-[53vh]' : 'h-[70vh]'
    ]">

      <!-- background -->
       <CommonBackgroundBannerBg
        :background= "bg"
        :isMobile = 'isMobile'
       />
      <!-- content -->
      <div :class="[
        'relative text-center px-6 mx-auto max-w-xl ',
        isMobile ? 'mt-[30px]' : 'ml-[40vw]' 
      ]">
        <h2 :class="[
          'welcome text-5xl md:text-7xl font-light tracking-[10px] select-none',
          ]">
         SABALI 
        </h2>
        <PagesHomeExploreButton/> 
      </div>
    </section>

    <!-- FEATURES -->
    <PagesHomeBrandCarousel
      :isMobile = 'isMobile'
      />

    <!-- PRODUCTS -->
    <section  class="px-6 sm:px-10 py-24 mt-[1vw]">

      <!-- Designed Toggler suitable to the website of design -->
      <div id="productToggle" class="mb-16 sticky top-0 z-30 bg-black/90 backdrop-blur-md py-4">
        <div class="relative flex border border-white/10 p-1 rounded-full bg-zinc-950 max-w-xs w-full mx-auto select-none">
          <!-- Slide Highlight overlay -->
          <div 
            class="absolute top-1 bottom-1 left-1 bg-white rounded-full transition-transform duration-500 ease-out"
            :style="{
              width: 'calc(50% - 4px)',
              transform: activeTab === 'men' ? 'translateX(0)' : 'translateX(100%)'
            }"
          ></div>

          <!-- Him Button -->
          <button 
            @click="activeTab = 'men'"
            class="relative z-10 flex-1 py-3 text-xs uppercase tracking-[0.25em] font-medium rounded-full text-center transition-colors duration-500"
            :class="activeTab === 'men' ? 'text-black' : 'text-white/50 hover:text-white'"
          >
            {{ $t('home.tab_men') }}
          </button>

          <!-- Her Button -->
          <button 
            @click="activeTab = 'women'"
            class="relative z-10 flex-1 py-3 text-xs uppercase tracking-[0.25em] font-medium rounded-full text-center transition-colors duration-500"
            :class="activeTab === 'women' ? 'text-black' : 'text-white/50 hover:text-white'"
          >
            {{ $t('home.tab_women') }}
          </button>
        </div>
      </div>

      <!-- Render components using Vue's built-in <component :is> with elegant transition -->
      <transition name="fade-slide" mode="out-in">
        <component :is="activeComponent" />
      </transition>

      <!-- Barchasi (All) Button -->
      <div :class="[
        'mt-12 flex justify-center',
        isMobile ? 'mt-[-200px]': ''
      ]">
        <button 
          @click="router.push('/products')"
          :class="[
            'px-10 py-3 border border-white/20  z-[999] rounded-[10px] hover:bg-white hover:text-black transition uppercase tracking-[0.25em] text-xs font-semibold',
            isMobile ? 'mt-[160px]' : 'mt-[10px]'
          ]"
        >
          {{ $t('home.barchasi') }}
        </button>
      </div>
    </section>
    
  </div>
</template>

<script setup>
import { ref, computed, onMounted, onUnmounted } from 'vue'
import { useRouter } from 'vue-router'
import banner from "~/assets/images/banners/banner1.png"
import mobileBanner from "~/assets/images/mobile-banner/2.jpg"
import PagesProductsMenParfumes from '~/components/pages/products/MenParfumes.vue'
import PagesProductsWomenParfumes from '~/components/pages/products/WomenParfumes.vue'

const router = useRouter()
const activeTab = ref('men')

const bg = ref(null)
const isMobile = ref(false)

// Computed property to switch component dynamically using Vue's built-in <component :is="...">
const activeComponent = computed(() => {
  return activeTab.value === 'men' ? PagesProductsMenParfumes : PagesProductsWomenParfumes
})

const checkIfMobile = () => {
  isMobile.value = window.innerWidth < 768 || /Mobi|Android|iPhone/i.test(navigator.userAgent)
  if (isMobile.value) {
    bg.value = mobileBanner
  } else {
    bg.value = banner
  }
}

onMounted(() => {
  checkIfMobile()
  window.addEventListener('resize', checkIfMobile)
  router.push('/')
})

onUnmounted(() => {
  window.removeEventListener('resize', checkIfMobile)
})
</script>

<style scoped>
.welcome{
     font-family: "Black Ops One", sans-serif;
}

/* Transition effects for collection tabs */
.fade-slide-enter-active,
.fade-slide-leave-active {
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
}

.fade-slide-enter-from {
  opacity: 0;
  transform: translateY(15px);
}

.fade-slide-leave-to {
  opacity: 0;
  transform: translateY(-15px);
}
</style>
