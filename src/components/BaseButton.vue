<script setup lang="ts">
defineProps<{
  type?: 'button' | 'submit' | 'reset'
}>()
</script>

<template>
  <button
    :type="type ?? 'button'"
    class="px-9 py-4 max-w-fit cursor-pointer mx-auto rounded-full bg-[#4C33FF] text-white font-medium text-base transition-colors duration-200 hover:bg-[#3726b5] focus:bg-[#3726b5] focus:outline-none"
  >
    <slot />
  </button>
</template>
