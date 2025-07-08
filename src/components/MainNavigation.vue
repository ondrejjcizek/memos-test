<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'
import IconDribble from '@/components/icons/IconDribble.vue'
import IconBehance from '@/components/icons/IconBehance.vue'

const isSticky = ref(false)
const mobileMenuOpen = ref(false)

function handleScroll() {
  isSticky.value = window.scrollY > 20
}

function toggleMobileMenu() {
  mobileMenuOpen.value = !mobileMenuOpen.value
}

function handleMobileNavClick() {
  if (mobileMenuOpen.value) {
    mobileMenuOpen.value = false
  }
}

onMounted(() => {
  window.addEventListener('scroll', handleScroll)
})

onUnmounted(() => {
  window.removeEventListener('scroll', handleScroll)
})
</script>

<template>
  <header
    class="fixed top-20 z-20 w-full transition-transform duration-300"
    :class="[isSticky ? 'translate-x-0 -translate-y-15' : '']"
  >
    <nav class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
      <div
        class="flex items-center justify-center py-4"
        :class="[
          isSticky
            ? 'bg-black/80 md:bg-transparent px-4 py-1 rounded-full'
            : 'px-4 py-1 rounded-full',
        ]"
      >
        <!-- Desktop Nav -->
        <ul
          class="hidden md:flex gap-8"
          :class="[
            'transition-colors duration-300',
            isSticky
              ? 'bg-black/80 backdrop-blur-sm px-4 py-2 rounded-full'
              : 'px-4 py-2 rounded-full',
          ]"
        >
          <li>
            <a class="text-white font-medium hover:text-blue-400 transition-colors" href="#home">
              Home
            </a>
          </li>
          <li>
            <a
              class="text-white font-medium hover:text-blue-400 transition-colors"
              href="#features"
            >
              Features
            </a>
          </li>
          <li>
            <a class="text-white font-medium hover:text-blue-400 transition-colors" href="#pricing">
              Pricing
            </a>
          </li>
          <li>
            <a class="text-white font-medium hover:text-blue-400 transition-colors" href="#blog">
              Blog
            </a>
          </li>
          <li class="flex items-center">
            <a href="https://dribbble.com/" aria-label="Dribbble" target="_blank">
              <IconDribble class="w-5 h-5 text-white hover:text-blue-400" />
            </a>
          </li>
          <li class="flex items-center">
            <a href="https://www.behance.net/" aria-label="Behance" target="_blank">
              <IconBehance class="w-5 h-5 text-white hover:text-blue-400" />
            </a>
          </li>
        </ul>

        <!-- hamburger -->
        <button
          @click="toggleMobileMenu"
          class="md:hidden text-white focus:outline-none focus:ring-2 focus:ring-blue-500"
        >
          <svg
            v-if="!mobileMenuOpen"
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M4 6h16M4 12h16M4 18h16"
            />
          </svg>
          <svg
            v-else
            xmlns="http://www.w3.org/2000/svg"
            class="h-6 w-6"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              stroke-width="2"
              d="M6 18L18 6M6 6l12 12"
            />
          </svg>
        </button>
      </div>

      <!-- mobile menu -->
      <transition name="fade">
        <ul
          v-if="mobileMenuOpen"
          class="flex flex-col gap-4 mt-2 bg-black/90 backdrop-blur-sm px-4 py-4 rounded-lg md:hidden"
        >
          <li>
            <a
              href="#home"
              @click="handleMobileNavClick"
              class="text-white font-medium hover:text-blue-400 transition-colors"
            >
              Home
            </a>
          </li>
          <li>
            <a
              href="#features"
              @click="handleMobileNavClick"
              class="text-white font-medium hover:text-blue-400 transition-colors"
            >
              Features
            </a>
          </li>
          <li>
            <a
              href="#pricing"
              @click="handleMobileNavClick"
              class="text-white font-medium hover:text-blue-400 transition-colors"
            >
              Pricing
            </a>
          </li>
          <li>
            <a
              href="#blog"
              @click="handleMobileNavClick"
              class="text-white font-medium hover:text-blue-400 transition-colors"
            >
              Blog
            </a>
          </li>
          <li class="flex items-center">
            <a
              href="https://dribbble.com/"
              target="_blank"
              aria-label="Dribbble"
              @click="handleMobileNavClick"
            >
              <IconDribble class="w-5 h-5 text-white hover:text-blue-400" />
            </a>
          </li>
          <li class="flex items-center">
            <a
              href="https://www.behance.net/"
              target="_blank"
              aria-label="Behance"
              @click="handleMobileNavClick"
            >
              <IconBehance class="w-5 h-5 text-white hover:text-blue-400" />
            </a>
          </li>
        </ul>
      </transition>
    </nav>
  </header>
</template>

<style scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.2s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
