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
      return 'text-sm md:text-base'
    case 'lg':
      return 'text-lg font-bold md:text-2xl'
    default:
      return 'md:text-[22px] text-lg'
  }
})
</script>

<template>
  <p :class="['text-white text-', alignClass, sizeClass]">
    <slot />
  </p>
</template>
