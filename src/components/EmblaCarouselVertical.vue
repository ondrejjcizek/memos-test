<script setup lang="ts">
import { ref, onMounted } from 'vue'
import emblaCarouselVue from 'embla-carousel-vue'
const [emblaRef, emblaApi] = emblaCarouselVue({ axis: 'y' })

const selectedIndex = ref(0)
const scrollSnaps = ref<number[]>([])

const canScrollPrev = ref(false)
const canScrollNext = ref(false)

function scrollTo(index: number) {
  if (emblaApi.value) emblaApi.value.scrollTo(index)
}
function updateSelected() {
  if (!emblaApi.value) return
  selectedIndex.value = emblaApi.value.selectedScrollSnap()
}

function updateButtons() {
  if (!emblaApi.value) return
  canScrollPrev.value = emblaApi.value.canScrollPrev()
  canScrollNext.value = emblaApi.value.canScrollNext()
}

onMounted(() => {
  if (!emblaApi.value) return

  scrollSnaps.value = emblaApi.value.scrollSnapList()
  updateSelected()
  updateButtons()
  emblaApi.value.on('select', () => {
    updateSelected()
    updateButtons()
  })
})
</script>

<template>
  <div class="relative mx-auto w-full max-w-7xl px-10">
    <div class="overflow-hidden" ref="emblaRef">
      <div class="flex h-[582px] flex-col">
        <slot />
      </div>
    </div>

    <div
      class="absolute top-1/2 -right-6 mt-8 flex -translate-y-1/2 rotate-90 justify-center gap-2 md:mt-12"
    >
      <button
        v-for="(_, index) in scrollSnaps"
        :key="index"
        @click="scrollTo(index)"
        :class="[
          'h-3 w-3 cursor-pointer rounded-full',
          selectedIndex === index ? 'bg-white' : 'border-[2px] border-white opacity-30',
        ]"
        aria-label="Go to slide"
      />
    </div>
  </div>
</template>
