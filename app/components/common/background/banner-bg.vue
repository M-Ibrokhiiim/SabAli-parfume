<template>
    <div class="absolute  flex justify-center inset-2 overflow-hidden">
        <img
           :src="background"
           :class="[
            'w-full h-full',
            isMobile ? 'border-none' : 'ml-[-100px] border-none'
            ]"
            alt="a"
        />
      </div>
</template>
<script setup>
defineProps({
    background: String,
    isMobile: Boolean
})

</script>