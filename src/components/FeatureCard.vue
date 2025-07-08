<script setup lang="ts">
import BaseText from './BaseText.vue'
import BaseTitle from './BaseTitle.vue'
</script>

<template>
  <article class="flex max-w-[271px] flex-col items-start text-left text-white">
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
