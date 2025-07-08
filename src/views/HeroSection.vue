<script setup lang="ts">
import MainNavigation from '@/components/MainNavigation.vue'
import BaseTitle from '@/components/BaseTitle.vue'
import BaseText from '@/components/BaseText.vue'
import EmblaCarousel from '@/components/EmblaCarousel.vue'
import BaseButton from '@/components/BaseButton.vue'
import BaseContainer from '@/components/BaseContainer.vue'
import BackgroundImageOverlay from '@/components/BackgroundImageOverlay.vue'
</script>

<template>
  <section class="relative flex items-center min-h-[850px]">
    <BackgroundImageOverlay filename="hero" :overlayOpacity="0.5" />
    <BaseContainer>
      <MainNavigation />
      <div class="relative w-full flex flex-col my-48">
        <EmblaCarousel class="mb-14 w-full">
          <div class="flex-none basis-full min-w-0 select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle size="xl" class="mb-7 max-w-3xl mx-auto">Forget About Code</BaseTitle>
            <BaseText class="max-w-3xl mx-auto"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
          <div class="flex-none basis-full min-w-0 select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle size="xl" class="mb-7 max-w-3xl mx-auto">Forget About Code</BaseTitle>
            <BaseText class="max-w-3xl mx-auto"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
          <div class="flex-none basis-full min-w-0 select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle size="xl" class="mb-7 max-w-3xl mx-auto">Forget About Code</BaseTitle>
            <BaseText class="max-w-3xl mx-auto"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
        </EmblaCarousel>
        <BaseButton center>Create an Account</BaseButton>
      </div>
    </BaseContainer>
  </section>
</template>
