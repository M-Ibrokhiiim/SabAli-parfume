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
        Barcha mahsulotlar
      </h2>
      <PagesProductsMenParfumes/>
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
