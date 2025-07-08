<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  size?: 'sm' | 'base' | 'lg'
  align?: 'left' | 'center' | 'right'
}>()

const alignClass = computed(() => {
  return props.align ? `text-${props.align}` : 'text-center'
})

const sizeClass = computed(() => {
  switch (props.size) {
    case 'sm':
      return 'text-sm font-normal leading-6 md:text-base md:leading-[26px]'
    case 'lg':
      return 'text-lg font-bold md:text-2xl'
    default:
      return 'text-lg md:text-[22px]'
  }
})
</script>

<template>
  <p :class="['text-white', alignClass, sizeClass]">
    <slot />
  </p>
</template>
