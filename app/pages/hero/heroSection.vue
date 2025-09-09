<template>
  <section class="hero-section relative h-screen text-white">
    <!-- Swiper Background -->
    <Swiper
        :modules="[Autoplay, EffectFade]"
        :autoplay="{ delay: 4000, disableOnInteraction: false }"
        effect="fade"
        loop
        class="h-full w-full"
    >
      <SwiperSlide
          v-for="(img, index) in heroImages"
          :key="index"
          class="relative h-screen"
      >
        <img
            :src="img"
            alt="Restaurant background"
            class="absolute inset-0 h-full w-full object-cover"
        />
        <!-- Overlay -->
        <div class="absolute inset-0 bg-black/60"></div>
      </SwiperSlide>
    </Swiper>

    <!-- Hero Content (overlayed on top of swiper) -->
    <div class="absolute inset-0 flex items-center justify-center text-center z-10">
      <div class="max-w-lg px-4 sm:max-w-xl md:max-w-2xl">
        <h1 class="text-4xl sm:text-5xl md:text-6xl font-bold uppercase tracking-wide mb-6">
          Welcome to Le Snacke
        </h1>
        <p class="text-lg sm:text-xl md:text-2xl mb-8 opacity-90">
          Savor exquisite flavors and unforgettable dining experiences in the heart of culinary delight.
        </p>
        <NuxtLink
            to="#menu"
            class="inline-block bg-[#0A9987] hover:bg-teal-700 text-white font-semibold py-3 px-6 rounded-lg transition-colors duration-300"
        >
          Explore Our Menu
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from 'swiper/vue';
import { Autoplay, EffectFade } from 'swiper/modules';

const heroImages = [
  'https://images.unsplash.com/photo-1517248135467-4c7edcad34c4',
  'https://images.unsplash.com/photo-1504674900247-0877df9cc836',
  'https://images.unsplash.com/photo-1600891964599-f61ba0e24092',
];
</script>
