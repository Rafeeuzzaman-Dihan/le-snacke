<template>
  <section class="hero-section relative h-screen flex items-center justify-center text-center text-white bg-[url('https://images.unsplash.com/photo-1517248135467-4c7edcad34c4')] bg-cover bg-center">
    <!-- Overlay for better text contrast -->
    <div class="absolute inset-0 bg-black/60"></div>

    <!-- Hero Content -->
    <div class="relative z-10 max-w-lg px-4 sm:max-w-xl md:max-w-2xl">
      <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold uppercase tracking-wide mb-6">
        Welcome to Le Snacke
      </h1>
      <p class="text-lg sm:text-xl md:text-2xl mb-8 opacity-90">
        Savor exquisite flavors and unforgettable dining experiences in the heart of culinary delight.
      </p>
      <NuxtLink
          to="/menu"
          class="inline-block bg-amber-500 hover:bg-amber-600 text-white font-semibold py-3 px-6 rounded-lg transition-colors duration-300"
      >
        Explore Our Menu
      </NuxtLink>
    </div>
  </section>
</template>

<script setup>
// No additional script setup logic needed for this simple hero section
</script>

<style scoped>
/* Tailwind handles most styling, but you can add custom scoped styles if needed */
</style>