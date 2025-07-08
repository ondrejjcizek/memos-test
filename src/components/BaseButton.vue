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
      'font-medium text-base cursor-pointer transition-colors duration-200 hover:filter hover:brightness-110 focus:brightness-110 focus:ring-1 focus:ring-blue-500 focus:ring-offset-0',
      iconOnly
        ? 'min-w-14 grid place-items-center aspect-square rounded-full'
        : 'px-9 py-4 rounded-full',
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
