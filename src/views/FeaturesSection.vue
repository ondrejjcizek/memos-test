<script setup lang="ts">
import BaseTitle from '@/components/BaseTitle.vue'
import BaseText from '@/components/BaseText.vue'
import FeatureCard from '@/components/FeatureCard.vue'
import IconDiamond from '@/components/icons/IconDiamond.vue'
import IconCopy from '@/components/icons/IconCopy.vue'
import BackgroundImageOverlay from '@/components/BackgroundImageOverlay.vue'
import BaseContainer from '@/components/BaseContainer.vue'
import EmblaCarouselVertical from '@/components/EmblaCarouselVertical.vue'
</script>

<template>
  <section id="features" class="relative flex min-h-[850px] items-center">
    <BackgroundImageOverlay filename="features" :overlayOpacity="0.6" />
    <BaseContainer>
      <div class="grid items-center gap-7 md:grid-cols-[1.5fr_3fr] lg:grid-cols-2">
        <div class="relative">
          <img
            src="/images/features-mockup.png"
            loading="lazy"
            srcset="/images/features-mockup@2x.png"
            alt="Features Mockup"
            class="-ml-1/2 top-1/2 right-0 my-10 w-full max-w-2xl md:absolute md:my-0 md:min-w-[983px] md:-translate-y-1/2"
          />
        </div>
        <EmblaCarouselVertical>
          <div class="mb-20 flex max-w-2xl flex-col">
            <div class="flex flex-col">
              <BaseTitle size="md" class="mb-4 md:mb-5" align="left"
                >We Create Something New</BaseTitle
              >
              <BaseText class="mb-10 max-w-xl md:mb-16" align="left"
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
          <div class="mb-20 flex max-w-2xl flex-col">
            <div class="flex flex-col">
              <BaseTitle size="md" class="mb-4 md:mb-5" align="left"
                >We Create Something New</BaseTitle
              >
              <BaseText class="mb-10 max-w-xl md:mb-16" align="left"
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
          <div class="mb-20 flex max-w-2xl flex-col">
            <div class="flex flex-col">
              <BaseTitle size="md" class="mb-4 md:mb-5" align="left"
                >We Create Something New</BaseTitle
              >
              <BaseText class="mb-10 max-w-xl md:mb-16" align="left"
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
          <div class="mb-20 flex max-w-2xl flex-col">
            <div class="flex flex-col">
              <BaseTitle size="md" class="mb-4 md:mb-5" align="left"
                >We Create Something New</BaseTitle
              >
              <BaseText class="mb-10 max-w-xl md:mb-16" align="left"
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
          <div class="flex max-w-2xl flex-col">
            <div class="flex flex-col">
              <BaseTitle size="md" class="mb-4 md:mb-5" align="left"
                >We Create Something New</BaseTitle
              >
              <BaseText class="mb-10 max-w-xl md:mb-16" align="left"
                >We have created a new product that will help designers, developers and companies
                create websites for their startups quickly and easily.</BaseText
              >
            </div>
            <div class="mb-6 flex gap-6">
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
        </EmblaCarouselVertical>
      </div>
    </BaseContainer>
  </section>
</template>
