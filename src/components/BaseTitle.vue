<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps<{
  level?: 1 | 2 | 3 | 4 | 5 | 6
  size?: 'xl' | 'lg' | 'md' | 'sm'
  align?: 'left' | 'center' | 'right'
}>()

const as = computed(() => {
  switch (props.level) {
    case 1:
      return 'h1'
    case 2:
      return 'h2'
    case 3:
      return 'h3'
    case 4:
      return 'h4'
    case 5:
      return 'h5'
    case 6:
      return 'h6'
    default:
      return 'h2'
  }
})

const alignClass = computed(() => {
  return props.align ? `text-${props.align}` : 'text-center'
})

const sizeClass = computed(() => {
  switch (props.size) {
    case 'xl':
      return 'lg:text-7xl md:text-6xl text-5xl leading-[1.2] tracking-[-1px]'
    case 'lg':
      return 'text-4xl md:text-[58px] leading-[70px] tracking-[-1px]'
    case 'md':
      return 'text-3xl md:text-[42px] tracking-[-0.4px]'
    case 'sm':
      return 'uppercase text-sm leading-[26px] tracking-[2px]'
    default:
      return 'text-4xl leading-tight'
  }
})
</script>

<template>
  <component :is="as" :class="['font-bold text-balance', alignClass, sizeClass, 'text-white']">
    <slot />
  </component>
</template>
