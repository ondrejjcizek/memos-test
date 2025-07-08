<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  level?: number
  align?: 'left' | 'center' | 'right'
}>()

const as = computed(() => {
  if (props.level === 1) return 'h1'
  if (props.level === 2) return 'h2'
  if (props.level === 3) return 'h3'
  return 'h2'
})

const alignClass = computed(() => {
  return props.align ? `text-${props.align}` : 'text-center'
})

const sizeClass = computed(() => {
  switch (props.level) {
    case 1:
      return 'lg:text-7xl leading-[1.2] md:text-6xl text-5xl'
    case 2:
      return 'text-3xl md:text-4xl'
    case 3:
      return 'text-xl md:text-2xl'
    default:
      return 'text-3xl md:text-4xl'
  }
})
</script>

<template>
  <component :is="as" :class="['font-bold', alignClass, sizeClass, 'text-white']">
    <slot />
  </component>
</template>
