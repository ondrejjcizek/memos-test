<script setup lang="ts">
defineProps<{
  type?: 'button' | 'submit' | 'reset'
  bgColor?: string
  iconOnly?: boolean
  center?: boolean
  fullWidth?: boolean
  ariaLabel?: string
}>()
</script>

<template>
  <button
    :type="type ?? 'button'"
    :aria-label="ariaLabel"
    :class="[
      'cursor-pointer text-base font-medium transition-colors duration-200 hover:brightness-110 hover:filter focus:ring-1 focus:ring-blue-500 focus:ring-offset-0 focus:brightness-110',
      iconOnly
        ? 'grid aspect-square min-w-14 place-items-center rounded-full'
        : 'rounded-full px-9 py-4',
      center ? 'mx-auto' : '',
      fullWidth ? 'w-full' : 'max-w-fit',
    ]"
    :style="{
      backgroundColor: bgColor ?? '#4C33FF',
      color: '#fff',
    }"
  >
    <slot />
  </button>
</template>
