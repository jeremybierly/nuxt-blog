<template>
  <header class="bg-white shadow">
    <nav class="container mx-auto px-4 py-6">
      <div class="flex justify-between items-center">
        <NuxtLink to="/" class="text-2xl font-bold text-gray-800">My Blog</NuxtLink>
        
        <!-- Desktop Navigation -->
        <div class="hidden md:flex space-x-4">
          <NuxtLink to="/" class="text-gray-600 hover:text-gray-800">Home</NuxtLink>
          <NuxtLink to="/about" class="text-gray-600 hover:text-gray-800">About</NuxtLink>
          <NuxtLink to="/projects" class="text-gray-600 hover:text-gray-800">Projects</NuxtLink>
        </div>
        
        <!-- Mobile Navigation -->
        <div class="md:hidden">
          <button @click="toggleMenu" class="text-gray-600 hover:text-gray-800">
            <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7" />
            </svg>
          </button>
        </div>
      </div>
      
      <!-- Mobile Menu -->
      <div v-if="isMenuOpen" class="md:hidden mt-4">
        <NuxtLink to="/" class="block py-2 text-gray-600 hover:text-gray-800">Home</NuxtLink>
        <NuxtLink to="/about" class="block py-2 text-gray-600 hover:text-gray-800">About</NuxtLink>
        <NuxtLink to="/projects" class="block py-2 text-gray-600 hover:text-gray-800">Projects</NuxtLink>
      </div>
    </nav>
  </header>
</template>

<script setup>
const isMenuOpen = ref(false)

const toggleMenu = () => {
  isMenuOpen.value = !isMenuOpen.value
}
</script>