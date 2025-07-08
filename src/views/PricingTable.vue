<script setup lang="ts">
import BaseContainer from '@/components/BaseContainer.vue'
import BaseText from '@/components/BaseText.vue'
import BaseTitle from '@/components/BaseTitle.vue'
import PricingCard from '@/components/PricingCard.vue'
</script>

<template>
  <section class="bg-[#2F1893] py-24">
    <BaseContainer>
      <BaseTitle class="mb-8" size="md">Plans & Pricing</BaseTitle>
      <BaseText class="max-w-[586px] mx-auto mb-14">
        Startup Framework is free forever — you only pay for custom domain hosting or to export your
        site.
      </BaseText>
      <div class="flex flex-wrap justify-center gap-8">
        <PricingCard
          planName="Starter"
          price="9.99"
          :features="[
            { label: '2 GB of space', available: true },
            { label: '14 days  of backups', available: true },
            { label: 'Social integrations', available: true },
            { label: 'Client billing', available: true },
            { label: 'Remote access', available: false },
            { label: 'Custom domain', available: false },
            { label: '24 hours support', available: false },
            { label: 'Admin tools', available: false },
            { label: 'Collaboration tools', available: false },
            { label: 'User management', available: false },
          ]"
        />
        <PricingCard
          planName="Professional"
          price="19.99"
          :features="[
            { label: '2 GB of space', available: true },
            { label: '14 days  of backups', available: true },
            { label: 'Social integrations', available: true },
            { label: 'Client billing', available: true },
            { label: 'Remote access', available: true },
            { label: 'Custom domain', available: true },
            { label: '24 hours support', available: true },
            { label: 'Admin tools', available: false },
            { label: 'Collaboration tools', available: false },
            { label: 'User management', available: false },
          ]"
        />
        <PricingCard
          planName="Team"
          price="49.99"
          :features="[
            { label: '2 GB of space', available: true },
            { label: '14 days  of backups', available: true },
            { label: 'Social integrations', available: true },
            { label: 'Client billing', available: true },
            { label: 'Remote access', available: true },
            { label: 'Custom domain', available: true },
            { label: '24 hours support', available: true },
            { label: 'Admin tools', available: true },
            { label: 'Collaboration tools', available: true },
            { label: 'User management', available: true },
          ]"
        />
      </div>
    </BaseContainer>
  </section>
</template>
