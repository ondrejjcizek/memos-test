<script setup lang="ts">
import BaseButton from './BaseButton.vue'
import IconCheck from './icons/IconCheck.vue'
defineProps<{
  planName: string
  price: string
  features: {
    label: string
    available: boolean
  }[]
}>()
</script>

<template>
  <article
    class="flex flex-col rounded-xl border-2 border-white/20 pt-12 pb-10 px-8 md:pt-16 md:pb-14 md:px-11 text-white w-full max-w-sm min-w-xs"
  >
    <header class="mb-6 text-left ml-5">
      <h2 class="text-[22px] font-medium tracking-wide mb-6">{{ planName }}</h2>
      <p class="text-4xl font-bold tracking-wide mb-6">
        {{ price }}<span class="align-top text-base font-normal ml-1">$</span>
      </p>
    </header>

    <ul class="flex-1 space-y-4 mb-6">
      <li
        v-for="(feature, index) in features"
        :key="index"
        class="flex items-center"
        :class="{ 'text-white/50': !feature.available }"
      >
        <template v-if="feature.available">
          <IconCheck class="w-4 h-4 mr-2 text-green-400" aria-hidden="true" />
        </template>
        <template v-else>
          <span class="w-5 h-5 mr-2"></span>
        </template>
        {{ feature.label }}
      </li>
    </ul>

    <footer class="text-center">
      <BaseButton fullWidth bgColor="transparent" class="rounded-full border-2 border-white/20">
        Get Started
      </BaseButton>
    </footer>
  </article>
</template>

<style scoped>
button:hover {
  background: #e93a7d !important;
  border-color: transparent !important;
}
</style>
