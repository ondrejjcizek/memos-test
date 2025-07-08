<script setup lang="ts">
const props = defineProps<{
  text: string
  for?: string
}>()
</script>

<template>
  <label
    :for="props.for"
    class="mb-3 block text-sm font-semibold tracking-[2px] text-[#1E0E62] uppercase"
  >
    {{ props.text }}
  </label>
</template>
