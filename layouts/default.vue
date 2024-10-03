<template>
  <div class="min-h-screen bg-gray-100">
    <TheHeader />
    <main class="container mx-auto px-4 py-8">
      <slot />
    </main>
    <footer class="bg-white shadow mt-8">
      <div class="container mx-auto px-4 py-6 text-center text-gray-600">
        &copy; {{ new Date().getFullYear() }} My Blog. All rights reserved.
      </div>
    </footer>
  </div>
</template>