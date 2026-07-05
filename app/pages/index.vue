<template>
  <div class="bg-black text-white">
    <!-- HERO -->
    <section class="h-[65vh] flex items-center justify-center relative">

      <!-- background -->
       <CommonBackgroundBannerBg
        :background= "banner"
       />
      <!-- content -->
      <div class="relative text-center px-6 ml-[90px]">
        <h2 class="welcome text-5xl md:text-7xl font-light tracking-[10px]">
         SABALI 
        </h2>

        <PagesHomeExploreButton/> 
        
      </div>
    </section>

    <!-- FEATURES -->
    <PagesHomeBrandCarousel  />

    <!-- PRODUCTS -->
    <section id="products" class="px-10 py-24 mt-[1vw] ">

      <h2 class="text-3xl tracking-[6px] text-center mb-16">
        FEATURED COLLECTION
      </h2>

      <div class="grid md:grid-cols-3 gap-10">

        <div class="group">
          <div class="overflow-hidden">
            <img
              src="https://images.unsplash.com/photo-1615634260167-c8cdede054de"
              class="h-[400px] w-full object-cover group-hover:scale-105 transition duration-500"
            />
          </div>
          <h3 class="mt-4 text-lg">Midnight Oud</h3>
          <p class="text-white/60 text-sm">Deep & mysterious scent</p>
        </div>

        <div class="group">
          <div class="overflow-hidden">
            <img
              src="https://media.vperfumes.com/products/Dior-Hypnotic-Poison-EDT-For-Women-30ML-1731388148036.webp"
              class="h-[400px] w-full object-cover group-hover:scale-105 transition duration-500"
            />
          </div>
          <h3 class="mt-4 text-lg">Velvet Rose</h3>
          <p class="text-white/60 text-sm">Soft floral elegance</p> 
        </div>
        <div class="group">
          <div class="overflow-hidden">
            <img
              src="https://i.ebayimg.com/images/g/2tQAAOSwx29lg04a/s-l1200.jpg"
              class="h-[400px] w-full object-cover group-hover:scale-105 transition duration-500"
            />
          </div> 
          <h3 class="mt-4 text-lg">Amber Noir</h3>
          <p class="text-white/60 text-sm">Warm and bold aroma</p>
        </div>
 <div>

 </div>
      </div>
    </section>
    
  </div>
</template>
<script setup>
const router  = useRouter()
import banner from "~/assets/images/banners/banner1.png"

onMounted(()=> {
router.push('/')
})
</script>
<style scoped>
.welcome{
     font-family: "Black Ops One", sans-serif;

}
</style>
