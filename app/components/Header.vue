<template>
  <header class="bg-[#0B2C4D] text-white">
    <div class="max-w-7xl mx-auto flex justify-between items-center py-3 px-6">
      <!-- Logo -->
      <div class="flex items-center gap-2">
        <div class="w-6 h-6 rounded-full border-2 border-white flex items-center justify-center">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="white">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 2C8.134 2 5 5.134 5 9c0 7 7 13 7 13s7-6 7-13c0-3.866-3.134-7-7-7z" />
          </svg>
        </div>
        <span class="text-lg font-semibold">Houzing</span>
      </div>

      <!-- Nav links -->
      <nav class="hidden md:flex gap-6">
        <a href="#" class="hover:text-gray-300">Home</a>
        <a href="#" class="hover:text-gray-300">Properties</a>
        <a href="#" class="hover:text-gray-300">Contacts</a>
      </nav>


      <!-- Login Button -->
      <button class="border border-white rounded-md px-5 py-1 hover:bg-white hover:text-[#0B2C4D] transition">
        Login
      </button>
    </div>

    <!-- Search Section -->
    <div class="bg-white py-4 px-6 shadow">
      <div class="max-w-7xl mx-auto flex flex-col md:flex-row items-center gap-2">
        <div class="flex items-center w-full border rounded-md px-3 py-2">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-5 h-5 text-blue-600 mr-2" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 10l9-7 9 7v11a1 1 0 01-1 1h-6v-7H10v7H4a1 1 0 01-1-1V10z" />
          </svg>
          <input type="text" placeholder="Enter an address, neighborhood, city, or ZIP code"
            class="w-full outline-none text-gray-700 placeholder-gray-500" />
        </div>

        <button @click="showModal = true" class="flex items-center gap-2 border rounded-md px-4 py-2 text-[#0B2C4D] hover:bg-gray-100">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 4v16m8-8H4" />
          </svg>
          Advanced
        </button>

        <button class="flex items-center gap-2 bg-blue-600 text-white rounded-md px-5 py-2 hover:bg-blue-700 transition">
          <svg xmlns="http://www.w3.org/2000/svg" class="w-4 h-4" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2"
              d="M21 21l-4.35-4.35m0 0A7.5 7.5 0 104.5 4.5a7.5 7.5 0 0012.15 12.15z" />
          </svg>
          Search
        </button>
      </div>
    </div>
    <div
      v-if="showModal"
      class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
    >
      <div class="bg-white p-6 rounded-lg w-full max-w-5xl">
        <div class="flex justify-between items-center mb-4">
          <h2 class="text-xl font-bold">Advanced Search</h2>
          <button @click="showModal = false" class="text-gray-500 hover:text-black">✕</button>
        </div>

        <form class="flex flex-col gap-8">
          <!-- Address -->
          <div>
            <h1 class="mb-4 text-bold text-2xl text-black">Address</h1>

          <input type="text" placeholder="Country" class="border p-2 rounded" />
          <input type="text" placeholder="Region" class="border p-2 rounded" />
          <input type="text" placeholder="City" class="border p-2 rounded" />
          <input type="text" placeholder="Zip code" class="border p-2 rounded" />
          </div>

          <!-- Apartment Info -->
          <div>
              <h1 class="mb-4 text-bold text-2xl text-black">Apartment Info</h1>

          <input type="text" placeholder="Rooms" class="border p-2 rounded" />
          <input type="text" placeholder="Size" class="border p-2 rounded" />
          <input type="text" placeholder="Sort" class="border p-2 rounded" />
          </div>

          <!-- Price --> 
          <div>
                      <h1 class="mb-4 text-bold text-2xl text-black">Price</h1>

          <input type="text" placeholder="Min price" class="border p-2 rounded" />
          <input type="text" placeholder="Max price" class="border p-2 rounded" />
          </div>
          <hr>
          <!-- Buttons -->
          <div class="col-span-2 md:col-span-4 flex justify-end gap-2 mt-2">
            <button type="button" @click="showModal = false" class="bg-gray-300 px-4 py-2 rounded">Cancel</button>
            <button type="submit" class="bg-blue-600 text-white px-4 py-2 rounded hover:bg-blue-700">Submit</button>
          </div>
        </form>
      </div>
    </div> 
  </header>
</template>
<script setup>
import { ref } from 'vue'

const showModal = ref(false)
</script>