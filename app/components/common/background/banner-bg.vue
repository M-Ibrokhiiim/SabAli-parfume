<template>
    <div class="absolute  flex justify-center inset-2 overflow-hidden">
        <img
           :src="background"
          :class="[
            'w-full h-full',
            isMobile ? '' : 'ml-[-300px]'
            ]"
        />
      </div>
</template>
<script setup>
const isMobile = ref(false)

defineProps({
    background: String 
})
 
</script>