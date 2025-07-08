<script setup lang="ts">
defineProps<{
  filename: string
  overlayOpacity: number
  eager?: boolean
}>()
</script>

<template>
  <div class="-z-1">
    <img
      :src="`/images/${filename}.jpg`"
      :srcset="`/images/${filename}@2x.jpg`"
      alt=""
      draggable="false"
      :loading="eager ? 'eager' : 'lazy'"
      decoding="async"
      width="1920"
      height="1080"
      class="absolute inset-0 z-1 h-full w-full object-cover select-none"
      :style="{ opacity: overlayOpacity }"
    />
    <div class="absolute inset-0 bg-[#2F1893]" />
  </div>
</template>
