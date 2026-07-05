<template>
    <div class="absolute  flex justify-center inset-2 overflow-hidden">
        <img
           :src="background"
          class="w-full h-full object-cover  ml-[-70px]"
        />
      </div>
</template>
<script setup>
defineProps({
    background: String 
})
 
</script>