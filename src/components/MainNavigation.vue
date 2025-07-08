<script setup lang="ts">
import IconDribble from '@/components/icons/IconDribble.vue'
import IconBehance from '@/components/icons/IconBehance.vue'
</script>

<template>
  <header class="absolute z-2 top-20 left-1/2 -translate-x-1/2">
    <nav>
      <ul class="flex gap-11 mx-auto max-w-fit">
        <li>
          <a
            class="text-white font-medium transition-colors duration-200 hover:text-blue-400 focus:text-blue-400"
            href="#"
            >Home</a
          >
        </li>
        <li>
          <a
            class="text-white font-medium transition-colors duration-200 hover:text-blue-400 focus:text-blue-400"
            href="#"
            >Features</a
          >
        </li>
        <li>
          <a
            class="text-white font-medium transition-colors duration-200 hover:text-blue-400 focus:text-blue-400"
            href="#"
            >Pricing</a
          >
        </li>
        <li>
          <a
            class="text-white font-medium transition-colors duration-200 hover:text-blue-400 focus:text-blue-400"
            href="#"
            >Blog</a
          >
        </li>
        <li
          class="flex items-center text-white transition-colors duration-200 hover:text-blue-400 focus:text-blue-400"
        >
          <a href="https://dribbble.com/" target="_blank"><IconDribble /></a>
        </li>
        <li
          class="flex items-center text-white transition-colors duration-200 hover:text-blue-400 focus:text-blue-400"
        >
          <a href="https://www.behance.net/" target="_blank"><IconBehance /></a>
        </li>
      </ul>
    </nav>
  </header>
</template>
