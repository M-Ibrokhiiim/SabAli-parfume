<template>
  <section id="products" class="px-10 py-24 bg-black">
      <!-- Designed Toggler suitable to the website of design -->
      <div id="productToggle" class="-mb-18  mt-[-70px] bg-black h-[100px] flex  items-center sticky top-0 z-[999]">
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

      <transition name="fade-slide" mode="out-in" >
        <component  :is="activeComponent" />
      </transition>
  </section>
</template>
<script setup>
import PagesProductsMenParfumes from '~/components/pages/products/MenParfumes.vue'
import PagesProductsWomenParfumes from '~/components/pages/products/WomenParfumes.vue'


const activeTab = ref('men')
const activeComponent = computed(() => {
  return activeTab.value === 'men' ? PagesProductsMenParfumes : PagesProductsWomenParfumes
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