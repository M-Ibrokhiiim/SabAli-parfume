<template>
  <div class="bg-black text-white">

    <!-- NAVBAR -->
    <header class="flex items-center justify-between px-10 py-6 border-b border-white/10">
      <h1 class="text-xl tracking-[6px] font-light">NOIR</h1>

      <nav class="hidden md:flex gap-10 text-sm text-white/70">
        <a href="#" class="hover:text-white transition">Home</a>
        <a href="#" class="hover:text-white transition">Collection</a>
        <a href="#" class="hover:text-white transition">About</a>
        <a href="#" class="hover:text-white transition">Contact</a>
      </nav>

      <button class="text-sm border border-white/30 px-4 py-2 hover:bg-white hover:text-black transition">
        Shop
      </button>
    </header>

    <!-- HERO -->
    <section class="h-[40vh] flex items-center justify-center relative">

      <!-- background -->
      <div class="absolute inset-0">
        <img
          src="https://images.unsplash.com/photo-1594035910387-fea47794261f"
          class="w-full h-full object-cover opacity-40"
        />
      </div>

      <!-- content -->
      <div class="relative text-center px-6">
        <h2 class="text-5xl md:text-7xl font-light tracking-[10px]">
         SAB ALI 
        </h2>

        <p class="mt-6 text-white/70 max-w-xl mx-auto">
          Discover exclusive fragrances crafted for timeless elegance and modern identity.
        </p>

        <button class="mt-10 px-8 py-3 border border-white/40 hover:bg-white hover:text-black transition">
          Explore Collection
        </button>
      </div>
    </section>

    <!-- FEATURES -->
    <section class="py-24 px-10 grid md:grid-cols-3 gap-10 text-center border-t border-white/10">

      <div>
        <h3 class="text-xl tracking-[4px]">SIGNATURE</h3>
        <p class="mt-4 text-white/60 text-sm">
          Unique perfumes designed with rare ingredients from around the world.
        </p>
      </div>

      <div>
        <h3 class="text-xl tracking-[4px]">LUXURY</h3>
        <p class="mt-4 text-white/60 text-sm">
          Minimal packaging with refined aesthetics and premium design.
        </p>
      </div>

      <div>
        <h3 class="text-xl tracking-[4px]">LIMITED</h3>
        <p class="mt-4 text-white/60 text-sm">
          Exclusive drops available in limited quantities only.
        </p>
      </div>

    </section>

    <!-- PRODUCTS -->
    <section class="px-10 py-24 border-t border-white/10">

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

      </div>
    </section>

    <!-- FOOTER -->
    <footer class="py-10 text-center text-white/50 border-t border-white/10 text-sm">
      © 2026 NOIR PERFUME. All rights reserved.
    </footer>

  </div>
</template>