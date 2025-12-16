<template>
  <div v-if="formModal.isOpen" class="fixed inset-0 bg-[#0000009e] z-40 flex items-center justify-center p-4">
    <div class="bg-white rounded-lg shadow-2xl max-w-2xl w-full animate-fade-in flex overflow-hidden">
      <!-- Left Side - Image -->
      <div class="hidden md:flex md:w-1/2 bg-gray-700 relative overflow-hidden items-center justify-center">
        <img src="/specs.png" alt="Background pattern" class="absolute inset-0 w-full h-full object-cover opacity-20" />
        <div class="relative z-10 flex items-center justify-center w-full h-full">
          <img src="/specs.png" alt="Person" class="h-full object-cover" />
        </div>
      </div>

      <!-- Right Side - Form -->
      <div class="w-full md:w-1/2 p-8">
        <!-- Header -->
        <div class="flex items-center justify-between mb-6">
          <h2 class="text-2xl font-semibold text-blue-900">REGISTER TO<br />LEARN MORE</h2>
          <button
            @click="formModal.closeModal"
            class="text-gray-400 hover:text-gray-600 transition-colors ml-4 shrink-0"
          >
            <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
            </svg>
          </button>
        </div>

        <!-- Form -->
        <form @submit.prevent="handleSubmit" class="space-y-6">
          <!-- First Name -->
          <div>
            <input
              v-model="formData.firstName"
              type="text"
              placeholder="First Name"
              class="w-full px-0 py-2 border-b border-gray-300 bg-transparent focus:outline-none focus:border-blue-900 transition text-sm"
            />
          </div>

          <!-- Last Name -->
          <div>
            <input
              v-model="formData.lastName"
              type="text"
              placeholder="Last Name"
              class="w-full px-0 py-2 border-b border-gray-300 bg-transparent focus:outline-none focus:border-blue-900 transition text-sm"
            />
          </div>

          <!-- Phone -->
          <div>
            <input
              v-model="formData.phone"
              type="tel"
              placeholder="Best Phone Number"
              class="w-full px-0 py-2 border-b border-gray-300 bg-transparent focus:outline-none focus:border-blue-900 transition text-sm"
            />
          </div>

          <!-- Email -->
          <div>
            <input
              v-model="formData.email"
              type="email"
              placeholder="Email"
              class="w-full px-0 py-2 border-b border-gray-300 bg-transparent focus:outline-none focus:border-blue-900 transition text-sm"
              required
            />
          </div>

          <!-- Checkbox -->
          <div class="flex items-center gap-3 py-4">
            <input
              v-model="formData.agreeToTerms"
              type="checkbox"
              id="agreement"
              class="w-4 h-4 rounded border-gray-300 cursor-pointer accent-blue-900"
            />
            <label for="agreement" class="text-sm text-gray-600 cursor-pointer">
              I'm not a robot
            </label>
            <svg class="w-5 h-5 text-blue-900 ml-auto" fill="currentColor" viewBox="0 0 20 20">
              <path fill-rule="evenodd" d="M10 18a8 8 0 100-16 8 8 0 000 16zM8.707 7.293a1 1 0 00-1.414 1.414L8.586 10l-1.293 1.293a1 1 0 101.414 1.414L10 11.414l1.293 1.293a1 1 0 001.414-1.414L11.414 10l1.293-1.293a1 1 0 00-1.414-1.414L10 8.586 8.707 7.293z" clip-rule="evenodd" />
            </svg>
          </div>

          <!-- Register Button -->
          <button
            type="submit"
            class="w-full bg-blue-900 text-white py-3 rounded-md font-semibold hover:bg-blue-800 transition-colors mt-8"
          >
            Register Now
          </button>
        </form>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { useFormModalStore } from '@/stores/formModal'

const formModal = useFormModalStore()

const formData = ref({
  firstName: '',
  lastName: '',
  phone: '',
  email: '',
  agreeToTerms: false
})

const handleSubmit = () => {
  console.log('Form submitted:', formData.value)
  formModal.closeModal()
  formData.value = {
    firstName: '',
    lastName: '',
    phone: '',
    email: '',
    agreeToTerms: false
  }
}
</script>

<style scoped>
@keyframes fade-in {
  from {
    opacity: 0;
    transform: scale(0.95);
  }
  to {
    opacity: 1;
    transform: scale(1);
  }
}

.animate-fade-in {
  animation: fade-in 0.3s ease-out;
}
</style>
