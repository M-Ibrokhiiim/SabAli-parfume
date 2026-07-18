<template>
  <div class="bg-black text-white overflow-hidden min-h-screen">
    
    <!-- Cinematic Editorial Hero -->
    <section class="h-[80vh] flex items-center justify-center relative select-none">
      <!-- High-fashion dark ambient overlay background -->
      <div class="absolute inset-0 z-0">
        <img
          src="https://images.unsplash.com/photo-1547887537-6158d64c35b3?q=80&w=1600&auto=format&fit=crop"
          class="w-full h-full object-cover opacity-50 filter grayscale contrast-125 transition-all duration-1000 transform hover:scale-105"
          alt="SabAli Parfume Editorial Background"
        />
        <div class="absolute inset-0 bg-gradient-to-b from-black/80 via-black/40 to-black"></div>
      </div>

      <!-- Hero Typography -->
      <div class="relative z-10 text-center px-6 max-w-4xl">
        <span class="text-xs uppercase tracking-[0.5em] text-white/50 block mb-6 animate-fade-in">
          {{ $t('about.founded') }}
        </span>
        <h1 class="text-5xl md:text-8xl font-light tracking-[0.15em] text-white uppercase leading-none mb-8">
          SABALI
          <span class="block text-2xl md:text-3xl font-serif italic text-white/60 tracking-[0.3em] lowercase mt-3">
            {{ $t('about.hero_sub') }}
          </span>
        </h1>
        <div class="h-12 w-[1px] bg-gradient-to-b from-white/40 to-transparent mx-auto"></div>
      </div>
    </section>

    <!-- Brand Philosophy & Founder's Manifesto -->
    <section class="py-32 px-6 sm:px-12 md:px-24 bg-black relative border-t border-white/5">
      <div class="max-w-4xl mx-auto text-center">
        <h2 class="text-xs uppercase tracking-[0.4em] text-white/40 mb-10">
          {{ $t('about.philosophy_title') }}
        </h2>
        <p class="text-2xl md:text-4xl font-serif font-light italic leading-relaxed text-white/90">
          {{ $t('about.philosophy_quote') }}
        </p>
        <p class="mt-8 text-sm font-sans tracking-[0.25em] text-white/40 uppercase">
          {{ $t('about.philosophy_author') }}
        </p>
      </div>
    </section>

    <!-- Alternating Story Chapters (Editorial Layout) -->
    <section class="pb-32 bg-black">
      <div class="max-w-7xl mx-auto px-6 sm:px-12 md:px-24 space-y-40">
        
        <!-- Chapter I: The Rare Sourcing -->
        <div class="grid md:grid-cols-2 gap-16 items-center">
          <div class="relative overflow-hidden rounded-2xl group border border-white/5">
            <!-- Image Frame -->
            <div class="aspect-[4/5] overflow-hidden">
              <img 
                src="https://images.unsplash.com/photo-1616949755610-8c9bbc08f138?q=80&w=800&auto=format&fit=crop" 
                class="w-full h-full object-cover transition-transform duration-1000 group-hover:scale-105"
                alt="Sourcing Rare Damask Roses"
              />
            </div>
            <!-- Overlay borders -->
            <div class="absolute inset-4 border border-white/10 pointer-events-none group-hover:border-white/20 transition-all duration-500"></div>
          </div>

          <div class="flex flex-col space-y-6">
            <span class="text-xs font-mono tracking-[0.3em] text-white/40 uppercase">
              {{ $t('about.ch1_num') }}
            </span>
            <h3 class="text-3xl sm:text-4xl font-light tracking-[0.1em] text-white uppercase">
              {{ $t('about.ch1_title') }}
            </h3>
            <p class="text-white/60 font-light leading-relaxed text-base">
              {{ $t('about.ch1_p1') }}
            </p>
            <p class="text-white/50 font-light leading-relaxed text-sm">
              {{ $t('about.ch1_p2') }}
            </p>
          </div>
        </div>

        <!-- Chapter II: The Alchemical Craft -->
        <div class="grid md:grid-cols-2 gap-16 items-center md:flex-row-reverse">
          <!-- Text column placed first for alternating order on desktop -->
          <div class="flex flex-col space-y-6 md:order-2">
            <span class="text-xs font-mono tracking-[0.3em] text-white/40 uppercase">
              {{ $t('about.ch2_num') }}
            </span>
            <h3 class="text-3xl sm:text-4xl font-light tracking-[0.1em] text-white uppercase">
              {{ $t('about.ch2_title') }}
            </h3>
            <p class="text-white/60 font-light leading-relaxed text-base">
              {{ $t('about.ch2_p1') }}
            </p>
            <p class="text-white/50 font-light leading-relaxed text-sm">
              {{ $t('about.ch2_p2') }}
            </p>
          </div>

          <!-- Image column -->
          <div class="relative overflow-hidden rounded-2xl group border border-white/5 md:order-1">
            <div class="aspect-[4/5] overflow-hidden">
              <img 
                src="https://images.unsplash.com/photo-1595425970377-c9703cf48b6d?q=80&w=800&auto=format&fit=crop" 
                class="w-full h-full object-cover transition-transform duration-1000 group-hover:scale-105"
                alt="Alchemical Perfume Distillation"
              />
            </div>
            <div class="absolute inset-4 border border-white/10 pointer-events-none group-hover:border-white/20 transition-all duration-500"></div>
          </div>
        </div>

      </div>
    </section>

    <!-- Brand Pillars Section -->
    <section class="py-32 px-6 sm:px-12 md:px-24 bg-zinc-950 border-y border-white/5 relative">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-20">
          <h2 class="text-xs uppercase tracking-[0.4em] text-white/40 mb-4">
            {{ $t('about.pillars_title') }}
          </h2>
          <p class="text-2xl font-light tracking-wide text-white/80">
            {{ $t('about.pillars_sub') }}
          </p>
        </div>

        <div class="grid md:grid-cols-3 gap-12">
          <!-- Pillar I -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <div class="h-10 w-10 text-white/40 flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8">
                <path stroke-linecap="round" stroke-linejoin="round" d="M11.48 3.499c-.195-.195-.51-.195-.706 0L4.316 9.957a.5.5 0 000 .707l6.458 6.458a.5.5 0 00.707 0l6.457-6.458a.5.5 0 000-.707L11.48 3.5z" />
                <path stroke-linecap="round" stroke-linejoin="round" d="M4.316 13.342l6.458 6.458a.5.5 0 00.707 0l6.457-6.458" />
              </svg>
            </div>
            <h3 class="text-lg font-light tracking-widest text-white uppercase pt-2">
              {{ $t('about.p1_title') }}
            </h3>
            <p class="text-sm font-light text-white/50 leading-relaxed">
              {{ $t('about.p1_desc') }}
            </p>
          </div>

          <!-- Pillar II -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <div class="h-10 w-10 text-white/40 flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8">
                <path stroke-linecap="round" stroke-linejoin="round" d="M12 21a9.004 9.004 0 008.716-6.747M12 21a9.004 9.004 0 01-8.716-6.747M12 21c2.485 0 4.5-4.03 4.5-9S14.485 3 12 3m0 18c-2.485 0-4.5-4.03-4.5-9S9.515 3 12 3m0 0a8.997 8.997 0 017.843 4.582M12 3a8.997 8.997 0 00-7.843 4.582" />
              </svg>
            </div>
            <h3 class="text-lg font-light tracking-widest text-white uppercase pt-2">
              {{ $t('about.p2_title') }}
            </h3>
            <p class="text-sm font-light text-white/50 leading-relaxed">
              {{ $t('about.p2_desc') }}
            </p>
          </div>

          <!-- Pillar III -->
          <div class="flex flex-col space-y-4 p-8 bg-black/40 border border-white/5 rounded-2xl hover:border-white/10 transition-colors duration-300">
            <div class="h-10 w-10 text-white/40 flex items-center justify-center">
              <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-8 h-8">
                <path stroke-linecap="round" stroke-linejoin="round" d="M21 8.25c0-2.485-2.099-4.5-4.688-4.5-1.935 0-3.597 1.126-4.312 2.733-.715-1.607-2.377-2.733-4.313-2.733C5.1 3.75 3 5.765 3 8.25c0 7.22 9 12 9 12s9-4.78 9-12z" />
              </svg>
            </div>
            <h3 class="text-lg font-light tracking-widest text-white uppercase pt-2">
              {{ $t('about.p3_title') }}
            </h3>
            <p class="text-sm font-light text-white/50 leading-relaxed">
              {{ $t('about.p3_desc') }}
            </p>
          </div>
        </div>
      </div>
    </section>

    <!-- Interactive Call-To-Action Atelier Banner -->
    <section class="h-[60vh] flex items-center justify-center relative select-none">
      <div class="absolute inset-0 z-0">
        <img
          src="https://images.unsplash.com/photo-1508746829417-e6f548d8d6ed?q=80&w=1600&auto=format&fit=crop"
          class="w-full h-full object-cover opacity-30 filter grayscale"
          alt="SabAli Atelier Interior"
        />
        <div class="absolute inset-0 bg-gradient-to-t from-black via-transparent to-black"></div>
      </div>

      <div class="relative z-10 text-center px-6 max-w-2xl flex flex-col items-center">
        <h2 class="text-3xl sm:text-5xl font-light tracking-[0.2em] text-white uppercase leading-tight mb-6">
          {{ $t('about.cta_title') }}
        </h2>
        <p class="text-white/60 font-light text-base leading-relaxed mb-10 max-w-lg">
          {{ $t('about.cta_desc') }}
        </p>
        <NuxtLink 
          to="/#products"
          class="px-10 py-4 bg-white text-black text-xs uppercase tracking-[0.3em] font-medium hover:bg-zinc-200 transition duration-300 shadow-xl"
        >
          {{ $t('about.cta_btn') }}
        </NuxtLink>
      </div>
    </section>

  </div>
</template>

<script setup>
// SabAli Premium Storytelling Script Setup
</script>

<style scoped>
.welcome {
  font-family: "Black Ops One", sans-serif;
}

@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(20px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

.animate-fade-in {
  animation: fadeIn 1.2s cubic-bezier(0.4, 0, 0.2, 1) forwards;
}
</style>