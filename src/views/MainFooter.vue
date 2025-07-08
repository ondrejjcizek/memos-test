<script setup lang="ts">
import BaseContainer from '@/components/BaseContainer.vue'
import BaseText from '@/components/BaseText.vue'
import IconTwitter from '@/components/icons/IconTwitter.vue'
import IconFacebook from '@/components/icons/IconFacebook.vue'
import IconGoogle from '@/components/icons/IconGoogle.vue'
</script>

<template>
  <footer class="bg-[#2F1893] py-12 md:py-16 lg:py-24">
    <BaseContainer>
      <div class="flex flex-wrap justify-between gap-4">
        <BaseText size="lg">Memos Test</BaseText>
        <div class="flex items-center gap-5 text-white">
          <a class="hover:underline" href="#policy">Privacy Policy</a>
          <a class="hover:underline" href="#terms">Terms</a>
          <a href="#twitter" aria-label="Twitter"><IconTwitter /></a>
          <a href="#facebook" aria-label="Facebook"><IconFacebook /></a>
          <a href="#googleplus" aria-label="Google Plus"><IconGoogle /></a>
        </div>
      </div>
      <hr class="border border-white/30 my-6 md:my-10" />
      <div class="flex flex-wrap justify-between gap-4">
        <div class="flex flex-wrap items-center gap-5 text-white">
          <a class="hover:underline" href="#tour">Tour</a>
          <a class="hover:underline" href="#features">Terms</a>
          <a class="hover:underline" href="#pricing">Pricing Plans</a>
          <a class="hover:underline" href="#works">Our works</a>
          <a class="hover:underline" href="#brands">Brands</a>
          <a class="hover:underline" href="#contacts">Contacts</a>
        </div>
        <BaseText size="sm">© 2025. All rights reserved.</BaseText>
      </div>
    </BaseContainer>
  </footer>
</template>
