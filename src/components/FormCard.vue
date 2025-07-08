<script setup lang="ts">
import { ref } from 'vue'
import BaseButton from './BaseButton.vue'
import FormLabel from './FormLabel.vue'
import ChevronDown from './icons/ChevronDown.vue'

const name = ref('')
const budget = ref('$500')
const email = ref('')
const message = ref('')
const sendCopy = ref(false)

const budgets = ['$500', '$1000', '$2000', '$5000']

const errors = ref({
  name: '',
  email: '',
  message: '',
})

function validateEmail(value: string) {
  return /^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(value)
}

function handleSubmit() {
  errors.value = {
    name: '',
    email: '',
    message: '',
  }

  let hasError = false

  if (!name.value.trim()) {
    errors.value.name = 'Name is required'
    hasError = true
  }
  if (!email.value.trim()) {
    errors.value.email = 'Email is required'
    hasError = true
  } else if (!validateEmail(email.value)) {
    errors.value.email = 'Invalid email format'
    hasError = true
  }
  if (!message.value.trim()) {
    errors.value.message = 'Message is required'
    hasError = true
  }

  if (hasError) {
    return
  }

  console.log('Form submitted:', {
    name: name.value,
    budget: budget.value,
    email: email.value,
    message: message.value,
    sendCopy: sendCopy.value,
  })

  // reset form
  name.value = ''
  budget.value = '$500'
  email.value = ''
  message.value = ''
  sendCopy.value = false
}
</script>

<template>
  <form
    @submit.prevent="handleSubmit"
    class="w-full max-w-lg space-y-6 rounded-xl bg-white px-12 py-14 shadow"
  >
    <!-- name + budget -->
    <div class="grid grid-cols-1 gap-4 md:grid-cols-2">
      <div>
        <FormLabel text="Your name" for="name" />
        <input
          id="name"
          v-model="name"
          type="text"
          placeholder="First name"
          class="w-full rounded-full border-2 border-[#EBEAED] px-4 py-2 text-lg text-gray-600 focus:ring-2 focus:ring-indigo-500 focus:outline-none"
        />
        <p v-if="errors.name" class="mt-1 text-xs text-red-500">{{ errors.name }}</p>
      </div>
      <div class="relative">
        <FormLabel text="Budget" for="budget" />
        <select
          id="budget"
          v-model="budget"
          class="w-full appearance-none rounded-full border-2 border-[#EBEAED] px-4 py-2 text-lg font-medium text-[#1E0E62] focus:ring-2 focus:ring-indigo-500 focus:outline-none"
        >
          <option v-for="b in budgets" :key="b" :value="b">{{ b }}</option>
        </select>
        <ChevronDown class="pointer-events-none absolute right-6 bottom-[20px] text-gray-500" />
      </div>
    </div>

    <!-- email -->
    <div>
      <FormLabel text="Your email" for="email" />
      <input
        id="email"
        v-model="email"
        type="email"
        placeholder="name@mail.com"
        class="w-full rounded-full border-2 border-[#EBEAED] px-4 py-2 text-lg text-gray-600 focus:ring-2 focus:ring-indigo-500 focus:outline-none"
      />
      <p v-if="errors.email" class="mt-1 text-xs text-red-500">{{ errors.email }}</p>
    </div>

    <!-- message -->
    <div>
      <FormLabel text="Your message" for="message" />
      <textarea
        id="message"
        v-model="message"
        placeholder="Message"
        rows="4"
        class="w-full rounded-xl border-2 border-[#EBEAED] px-4 py-2 text-lg text-gray-600 focus:ring-2 focus:ring-indigo-500 focus:outline-none"
      ></textarea>
      <p v-if="errors.message" class="mt-1 text-xs text-red-500">{{ errors.message }}</p>
    </div>

    <!-- checkbox -->
    <div class="flex flex-col items-center justify-between gap-6 sm:flex-row sm:gap-4">
      <label class="flex items-center space-x-2 text-lg">
        <input
          v-model="sendCopy"
          type="checkbox"
          class="h-5 w-5 rounded border-teal-300 accent-[#25DAC5] focus:ring-0"
        />
        <span class="font-light text-gray-400">Send me a copy</span>
      </label>
      <BaseButton class="min-w-[120px] text-lg" bgColor="#25DAC5" type="submit">Send</BaseButton>
    </div>
  </form>
</template>
