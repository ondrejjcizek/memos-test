<script setup lang="ts">
import MainNavigation from '@/components/MainNavigation.vue'
import BaseTitle from './BaseTitle.vue'
import BaseText from './BaseText.vue'
import EmblaCarousel from './EmblaCarousel.vue'
import BaseButton from './BaseButton.vue'
import BaseContainer from './BaseContainer.vue'
</script>

<template>
  <div class="relative flex items-center min-h-[850px]">
    <img
      src="/images/hero.jpg"
      alt="Landing Page Background"
      draggable="false"
      class="w-full h-full object-cover inset-0 absolute z-1 opacity-50 select-none"
      srcset="/images/hero@2x.jpg"
    />
    <div class="absolute h-full inset-0 bg-[#2F1893]"></div>
    <BaseContainer>
      <MainNavigation />
      <div class="relative z-1 w-full flex flex-col my-48">
        <EmblaCarousel class="mb-14 w-full">
          <div class="flex-none basis-full min-w-0 select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle :level="1" class="mb-7 max-w-3xl mx-auto">Forget About Code</BaseTitle>
            <BaseText class="max-w-3xl mx-auto"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
          <div class="flex-none basis-full min-w-0 select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle :level="1" class="mb-7 max-w-3xl mx-auto">Forget About Code</BaseTitle>
            <BaseText class="max-w-3xl mx-auto"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
          <div class="flex-none basis-full min-w-0 select-none">
            <BaseText size="lg" class="mb-7">Startup 3</BaseText>
            <BaseTitle :level="1" class="mb-7 max-w-3xl mx-auto">Forget About Code</BaseTitle>
            <BaseText class="max-w-3xl mx-auto"
              >Startup Framework gives you complete freedom over your creative process — you don’t
              have to think about any technical aspects. There are no limits and absolutely no
              coding.
            </BaseText>
          </div>
        </EmblaCarousel>
        <BaseButton>Create an Account</BaseButton>
      </div>
    </BaseContainer>
  </div>
</template>
