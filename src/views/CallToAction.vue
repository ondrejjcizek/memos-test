<script setup lang="ts">
import BaseContainer from '@/components/BaseContainer.vue'
import BaseTitle from '@/components/BaseTitle.vue'
import BackgroundImageOverlay from '@/components/BackgroundImageOverlay.vue'
import BaseText from '@/components/BaseText.vue'
import BaseButton from '@/components/BaseButton.vue'
import IconPlay from '@/components/icons/IconPlay.vue'
</script>

<template>
  <section class="relative flex items-center min-h-[605px]">
    <BackgroundImageOverlay filename="callToAction" :overlayOpacity="0.7" />
    <BaseContainer class="flex flex-col items-center">
      <BaseTitle size="lg" class="mb-6">
        Easy to setup.<br />
        Easy to maintain
      </BaseTitle>
      <BaseText class="max-w-[518px] mx-auto mb-14">
        Bootstrap is a widely-used, sleek, intuitive and powerful front-end framework for faster and
        easier web development.
      </BaseText>
      <div class="flex gap-[30px]">
        <BaseButton iconOnly bgColor="#EA3223" ariaLabel="Play video"><IconPlay /></BaseButton>
        <BaseButton bgColor="#25DAC5">Get Started</BaseButton>
      </div>
    </BaseContainer>
  </section>
</template>
