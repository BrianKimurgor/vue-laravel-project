<template>
  <section class="bg-gray-800 py-16 px-4">
    <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center justify-center gap-12">
      <!-- Left side - Image placeholder -->
      <div class="hidden md:block md:w-1/2">
        <div class="bg-gray-700 rounded-lg h-80 flex items-center justify-center">
          <span class="text-gray-500 text-lg">Image Placeholder</span>
        </div>
      </div>

      <!-- Right side - Form -->
      <div class="w-full md:w-1/2 bg-white rounded-lg p-8 shadow-lg">
        <h3 class="text-2xl font-semibold text-blue-900 mb-6">
          REGISTER TO LEARN<br />MORE
        </h3>

        <form class="space-y-4">
          <!-- Last Name -->
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1">Last Name</label>
            <input
              type="text"
              placeholder="Last Name"
              class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-blue-900 focus:border-transparent outline-none"
            />
          </div>

          <!-- Email -->
          <div>
            <label class="block text-sm font-medium text-gray-700 mb-1">Email</label>
            <input
              type="email"
              placeholder="user@email.com"
              class="w-full px-4 py-2 border border-gray-300 rounded-md focus:ring-2 focus:ring-blue-900 focus:border-transparent outline-none"
            />
          </div>

          <!-- Checkbox -->
          <div class="flex items-center gap-2 py-2">
            <input
              type="checkbox"
              id="agreement"
              class="w-4 h-4 rounded border-gray-300 cursor-pointer accent-blue-900"
            />
            <label for="agreement" class="text-sm text-gray-600 cursor-pointer">
              I read the Agreement
            </label>
          </div>

          <!-- Register Button -->
          <button
            type="submit"
            class="w-full bg-blue-900 text-white py-3 rounded-md font-semibold hover:bg-blue-800 transition-colors mt-6"
          >
            Register Now
          </button>
        </form>
      </div>
    </div>
  </section>
</template>

<script setup lang="ts">
// Form Section component
</script>

<style scoped>
/* Component styles are handled by Tailwind CSS */
</style>
