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
defineProps({
    background: String,
    isMobile: Boolean
})

</script>