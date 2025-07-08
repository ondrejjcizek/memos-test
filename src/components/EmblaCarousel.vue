<script setup lang="ts">
import { ref, onMounted } from 'vue'
import emblaCarouselVue from 'embla-carousel-vue'
import IconChevronLeft from './icons/IconChevronLeft.vue'
import IconChevronRight from './icons/IconChevronRight.vue'

const [emblaRef, emblaApi] = emblaCarouselVue()

const selectedIndex = ref(0)
const scrollSnaps = ref<number[]>([])

const canScrollPrev = ref(false)
const canScrollNext = ref(false)

function scrollTo(index: number) {
  if (emblaApi.value) emblaApi.value.scrollTo(index)
}
function scrollPrev() {
  if (emblaApi.value) emblaApi.value.scrollPrev()
}
function scrollNext() {
  if (emblaApi.value) emblaApi.value.scrollNext()
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
  <div class="relative px-12 max-w-7xl mx-auto">
    <div class="overflow-hidden" ref="emblaRef">
      <div class="flex w-full">
        <slot />
      </div>
    </div>
    <button
      @click="scrollPrev"
      :disabled="!canScrollPrev"
      class="absolute left-0 top-1/2 -translate-y-1/2 cursor-pointer disabled:opacity-50 disabled:pointer-events-none"
      aria-label="Previous slide"
    >
      <IconChevronLeft />
    </button>
    <button
      @click="scrollNext"
      :disabled="!canScrollNext"
      class="absolute right-0 top-1/2 -translate-y-1/2 cursor-pointer disabled:opacity-50 disabled:pointer-events-none"
      aria-label="Next slide"
    >
      <IconChevronRight />
    </button>
    <div class="flex justify-center md:mt-12 mt-8 gap-2">
      <button
        v-for="(_, index) in scrollSnaps"
        :key="index"
        @click="scrollTo(index)"
        :class="[
          'w-3 h-3 rounded-full cursor-pointer',
          selectedIndex === index ? 'bg-white' : 'border-[2px] border-white opacity-30',
        ]"
        aria-label="Go to slide"
      />
    </div>
  </div>
</template>
