<script setup lang="ts">
import BaseTitle from '@/components/BaseTitle.vue'
import BaseText from '@/components/BaseText.vue'
import EmblaCarousel from '@/components/EmblaCarousel.vue'
import BaseButton from '@/components/BaseButton.vue'
import BaseContainer from '@/components/BaseContainer.vue'
import BackgroundImageOverlay from '@/components/BackgroundImageOverlay.vue'
</script>

<template>
  <section id="home" class="relative flex min-h-[850px] items-center">
    <BackgroundImageOverlay eager filename="hero" :overlayOpacity="0.5" />
    <BaseContainer>
      <!-- <MainNavigation /> -->
      <div class="relative my-48 flex w-full flex-col">
        <EmblaCarousel class="mb-14 w-full">
          <div class="min-w-0 flex-none basis-full select-none">
            <BaseText size="lg" class="mb-7">Memos Test</BaseText>
            <BaseTitle size="xl" class="mx-auto mb-7 max-w-3xl">Forget About Code</BaseTitle>
            <BaseText class="mx-auto max-w-3xl"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
          <div class="min-w-0 flex-none basis-full select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle size="xl" class="mx-auto mb-7 max-w-3xl">Forget About Code</BaseTitle>
            <BaseText class="mx-auto max-w-3xl"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
          <div class="min-w-0 flex-none basis-full select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle size="xl" class="mx-auto mb-7 max-w-3xl">Forget About Code</BaseTitle>
            <BaseText class="mx-auto max-w-3xl"
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
