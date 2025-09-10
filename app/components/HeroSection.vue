<template>
  <section class="hero-section relative h-screen text-white overflow-hidden">
    <!-- Background Image -->
    <img
        src="/images/hero1.jpg"
        alt="Hero Background"
        class="absolute inset-0 h-full w-full object-cover animate-zoom-slow"
    />
    <!-- Gradient Overlay -->
    <div class="absolute inset-0 bg-gradient-to-b from-black/70 via-black/40 to-black/70"></div>

    <!-- Hero Content -->
    <div class="absolute inset-0 flex flex-col items-center justify-center text-center z-10 px-4">
      <h1 class="hero-title text-4xl sm:text-5xl md:text-6xl font-bold uppercase tracking-wide mb-6">
        <span class="line line1">Welcome to</span><br />
        <span class="line line2">Le Snacke</span>
      </h1>
      <p class="hero-subtitle text-lg sm:text-xl md:text-2xl mb-8 opacity-90 animate-fade-up">
        Savor exquisite flavors and unforgettable dining experiences in the heart of culinary delight.
      </p>
      <ExploreMenuBtn />
    </div>
  </section>
</template>

<style scoped>
/* Slow zoom for background */
@keyframes zoom-slow {
  0% { transform: scale(1.1); }
  100% { transform: scale(1); }
}
.animate-zoom-slow {
  animation: zoom-slow 20s ease-in-out infinite alternate;
}

/* Line slide-up animation */
.hero-title .line {
  display: inline-block;
  opacity: 0;
  transform: translateY(50%);
  animation: slide-up 0.8s forwards;
}
.hero-title .line1 {
  animation-delay: 0.3s;
}
.hero-title .line2 {
  animation-delay: 0.6s;
}
@keyframes slide-up {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* Subtitle fade-up */
.animate-fade-up {
  opacity: 0;
  transform: translateY(20px);
  animation: fade-up 0.8s forwards 0.9s;
}
@keyframes fade-up {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
<script setup lang="ts">
import ExploreMenuBtn from "~/components/common/ExploreMenuBtn.vue";
</script>