<script setup lang="ts">
import { ref, onMounted } from 'vue'
import emblaCarouselVue from 'embla-carousel-vue'
import IconChevronLeft from './icons/IconChevronLeft.vue'
import IconChevronRight from './icons/IconChevronRight.vue'

// Call emblaCarouselVue() INSIDE setup so each component instance gets a unique ref & API
const [emblaRef, emblaApi] = emblaCarouselVue()

const selectedIndex = ref(0)
const scrollSnaps = ref<number[]>([])

const canScrollPrev = ref(false)
const canScrollNext = ref(false)

function scrollTo(index: number) {
  emblaApi.value?.scrollTo(index)
}
function scrollPrev() {
  emblaApi.value?.scrollPrev()
}
function scrollNext() {
  emblaApi.value?.scrollNext()
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
      <div class="flex w-full">
        <slot />
      </div>
    </div>
    <button
      @click="scrollPrev"
      :disabled="!canScrollPrev"
      class="absolute top-1/2 left-0 -translate-y-1/2 cursor-pointer disabled:pointer-events-none disabled:opacity-50"
      aria-label="Previous slide"
    >
      <IconChevronLeft />
    </button>
    <button
      @click="scrollNext"
      :disabled="!canScrollNext"
      class="absolute top-1/2 right-0 -translate-y-1/2 cursor-pointer disabled:pointer-events-none disabled:opacity-50"
      aria-label="Next slide"
    >
      <IconChevronRight />
    </button>
    <div class="mt-8 flex justify-center gap-2 md:mt-12">
      <button
        v-for="(_, index) in scrollSnaps"
        :key="index"
        @click="scrollTo(index)"
        :class="[
          'h-3 w-3 cursor-pointer rounded-full',
          selectedIndex === index ? 'bg-white' : 'border-[2px] border-white/100 opacity-30',
        ]"
        aria-label="Go to slide"
      />
    </div>
  </div>
</template>
