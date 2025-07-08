<script setup lang="ts">
import BaseText from '@/components/BaseText.vue'
import BaseTitle from '@/components/BaseTitle.vue'
import BackgroundImageOverlay from '@/components/BackgroundImageOverlay.vue'
import BaseContainer from '@/components/BaseContainer.vue'
import IconPhone from '@/components/icons/IconPhone.vue'
import IconMail from '@/components/icons/IconMail.vue'
import IconCompany from '@/components/icons/IconCompany.vue'
import FormCard from '@/components/FormCard.vue'
</script>

<template>
  <section class="relative flex items-center min-h-[770px]">
    <BackgroundImageOverlay filename="contact" :overlayOpacity="0.6" />
    <BaseContainer
      class="flex flex-col md:flex-row items-center justify-center gap-12 md:gap-20 my-20 md:my-10"
    >
      <div class="flex flex-col items-start gap-11">
        <BaseTitle align="left" size="md" class="-mb-4">Let's Keep in Touch</BaseTitle>
        <BaseText align="left" class="max-w-[399px]">
          We have created a new product that will help designers, developers and companies create
          websites for their startups quickly and easily.
        </BaseText>
        <BaseText class="flex items-start gap-3" size="sm">
          <IconPhone class="relative top-1" />
          <a href="tel:+15555055050">+1 555 505 5050</a>
        </BaseText>
        <BaseText class="flex items-start gap-3" size="sm">
          <IconMail class="relative top-1" />
          <a href="mailto:info@designmodo.com">info@designmodo.com</a>
        </BaseText>
        <BaseText class="flex items-start gap-3" align="left" size="sm">
          <IconCompany class="relative top-1" />
          <div class="max-w-[252px]">
            San Francisco, CA560 Bush St & 20th Ave, Apt5 San Francisco, 230909
          </div>
        </BaseText>
      </div>
      <FormCard />
    </BaseContainer>
  </section>
</template>
