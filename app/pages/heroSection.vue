<template>
  <section class="hero-section relative h-screen text-white overflow-hidden">
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
            class="absolute inset-0 h-full w-full object-cover scale-110 animate-zoom-slow"
        />
        <!-- Gradient Overlay -->
        <div class="absolute inset-0 bg-gradient-to-b from-black/70 via-black/40 to-black/70"></div>
      </SwiperSlide>
    </Swiper>

    <!-- Hero Content -->
    <div class="absolute inset-0 flex items-center justify-center text-center z-10">
      <div class="max-w-lg px-4 sm:max-w-xl md:max-w-2xl">
        <!-- Split text animation container -->
        <h1
            class="hero-title text-4xl sm:text-5xl md:text-6xl font-bold uppercase tracking-wide mb-6"
        >
          Welcome to Le Snacke
        </h1>
        <p
            class="hero-subtitle text-lg sm:text-xl md:text-2xl mb-8 opacity-90"
        >
          Savor exquisite flavors and unforgettable dining experiences in the heart of culinary delight.
        </p>
        <NuxtLink
            to="#menu"
            class="group inline-block bg-[#0A9987] text-white font-semibold py-3 px-6 rounded-lg transition-all duration-300 relative overflow-hidden"
        >
          <span class="relative z-10">Explore Our Menu</span>
          <!-- Glow hover -->
          <span
              class="absolute inset-0 bg-gradient-to-r from-teal-400 to-teal-600 translate-y-full group-hover:translate-y-0 transition-transform duration-300"
          ></span>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Autoplay, EffectFade } from "swiper/modules";

const heroImages = [
  "https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=1920&q=80",
  "https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1920&q=80",
  "https://images.unsplash.com/photo-1600891964599-f61ba0e24092?auto=format&fit=crop&w=1920&q=80",
];
</script>

<style scoped>
/* Subtle slow zoom effect for background images */
@keyframes zoom-slow {
  0% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}
.animate-zoom-slow {
  animation: zoom-slow 10s ease-in-out infinite alternate;
}

/* Split text reveal */
.hero-title {
  overflow: hidden;
}
.hero-title span {
  display: inline-block;
  transform: translateY(100%);
  animation: slide-up 0.8s ease forwards;
}
@keyframes slide-up {
  to {
    transform: translateY(0%);
  }
}
</style>
