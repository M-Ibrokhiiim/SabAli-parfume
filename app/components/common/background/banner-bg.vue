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
import { ref, onMounted, onUnmounted } from 'vue'

const isMobile = ref(false)

defineProps({
    background: String 
})

const checkIfMobile = () => {
  isMobile.value = window.innerWidth < 768 || /Mobi|Android|iPhone/i.test(navigator.userAgent)
}

onMounted(() => {
  checkIfMobile()
  window.addEventListener('resize', checkIfMobile)
})

onUnmounted(() => {
  window.removeEventListener('resize', checkIfMobile)
})
</script>