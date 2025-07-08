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
    class="flex w-full max-w-sm min-w-xs flex-col rounded-xl border-2 border-white/20 px-8 pt-12 pb-10 text-white md:px-11 md:pt-16 md:pb-14"
  >
    <header class="mb-6 ml-5 text-left">
      <h2 class="mb-6 text-[22px] font-medium tracking-wide">{{ planName }}</h2>
      <p class="mb-6 text-4xl font-bold tracking-wide">
        {{ price }}<span class="ml-1 align-top text-base font-normal">$</span>
      </p>
    </header>

    <ul class="mb-6 flex-1 space-y-4">
      <li
        v-for="(feature, index) in features"
        :key="index"
        class="flex items-center"
        :class="{ 'text-white/50': !feature.available }"
      >
        <template v-if="feature.available">
          <IconCheck class="mr-2 h-4 w-4 text-green-400" aria-hidden="true" />
        </template>
        <template v-else>
          <span class="mr-2 h-5 w-5"></span>
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
