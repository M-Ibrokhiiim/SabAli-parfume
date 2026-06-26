<template>
     <header class="flex items-center  bg-black justify-between px-10 py-6 border-b border-white/10">
      <h1 class="text-xl tracking-[6px] font-light text-white">NOIR</h1>

      <nav class="hidden md:flex gap-10 text-sm text-white/70">
        <NuxtLink href="/" class="hover:text-white transition">Home</NuxtLink>
        <NuxtLink href="collections" class="hover:text-white transition">Collection</NuxtLink>
        <NuxtLink href="about" class="hover:text-white transition">About</NuxtLink>
        <NuxtLink href="contact" class="hover:text-white transition">Contact</NuxtLink>
      </nav>

      <button class="text-sm border text-white border-white/30 px-4 py-2 hover:bg-white hover:text-black transition">
        Shop
      </button>
    </header>
</template>
<script setup>

</script>