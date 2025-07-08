<script setup lang="ts">
defineProps<{
  filename: string
  overlayOpacity: number
}>()
</script>

<template>
  <div class="-z-1">
    <img
      :src="`/images/${filename}.jpg`"
      :srcset="`/images/${filename}@2x.jpg`"
      alt="Background"
      draggable="false"
      class="w-full h-full object-cover inset-0 absolute z-1 select-none"
      :style="{ opacity: overlayOpacity }"
    />
    <div class="absolute inset-0 bg-[#2F1893]" />
  </div>
</template>
