<script setup lang="ts">
import BaseTitle from '@/components/BaseTitle.vue'
import BaseText from '@/components/BaseText.vue'
import FeatureCard from '@/components/FeatureCard.vue'
import IconDiamond from '@/components/icons/IconDiamond.vue'
import IconCopy from '@/components/icons/IconCopy.vue'
import BackgroundImageOverlay from '@/components/BackgroundImageOverlay.vue'
import BaseContainer from '@/components/BaseContainer.vue'
</script>

<template>
  <div class="relative flex items-center min-h-[850px]">
    <BackgroundImageOverlay filename="features" :overlayOpacity="0.6" />
    <BaseContainer>
      <div class="grid lg:grid-cols-2 md:grid-cols-[1.5fr_3fr] items-center gap-7">
        <div class="relative">
          <img
            src="/images/features-mockup.png"
            srcset="/images/features-mockup@2x.png"
            alt="Features Mockup"
            class="md:absolute right-0 top-1/2 md:-translate-y-1/2 max-w-2xl -ml-1/2 md:min-w-[983px] w-full mb-6 md:md-0"
          />
        </div>
        <div class="flex flex-col max-w-2xl">
          <div class="flex flex-col">
            <BaseTitle size="md" class="mb-4 md:mb-5" align="left"
              >We Create Something New</BaseTitle
            >
            <BaseText class="md:mb-16 mb-10 max-w-xl" align="left"
              >We have created a new product that will help designers, developers and companies
              create websites for their startups quickly and easily.</BaseText
            >
          </div>
          <div class="flex gap-6">
            <FeatureCard>
              <template #icon>
                <IconCopy />
              </template>
              <template #title> 30 New Feature Pages </template>
              <template #description>
                Startup Framework contains components and complex blocks which can easily.
              </template>
            </FeatureCard>
            <FeatureCard>
              <template #icon>
                <IconDiamond />
              </template>
              <template #title> 30 New Feature Pages </template>
              <template #description>
                Startup Framework contains components and complex blocks which can easily.
              </template>
            </FeatureCard>
          </div>
        </div>
      </div>
    </BaseContainer>
  </div>
</template>
