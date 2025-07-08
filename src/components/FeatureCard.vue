<script setup lang="ts">
import BaseText from './BaseText.vue'
import BaseTitle from './BaseTitle.vue'
</script>

<template>
  <article class="flex flex-col items-start text-white text-left max-w-[271px]">
    <div class="mb-6">
      <slot name="icon" />
    </div>
    <BaseTitle align="left" class="mb-6" :level="3" size="sm">
      <slot name="title" />
    </BaseTitle>
    <BaseText align="left" size="sm">
      <slot name="description" />
    </BaseText>
  </article>
</template>
