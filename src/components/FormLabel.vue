<script setup lang="ts">
const props = defineProps<{
  text: string
  for?: string
}>()
</script>

<template>
  <label
    :for="props.for"
    class="block text-sm uppercase tracking-[2px] font-semibold text-[#1E0E62] mb-3"
  >
    {{ props.text }}
  </label>
</template>
