<template>
  <section class="hero-section relative h-screen text-white overflow-hidden">
    <!-- Background Image -->
    <img
        src="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=1920&q=80"
        alt="Hero Background"
        class="absolute inset-0 h-full w-full object-cover animate-zoom-slow"
    />
    <div class="absolute inset-0 bg-gradient-to-b from-black/70 via-black/40 to-black/70"></div>

    <!-- Hero Content -->
    <div class="absolute inset-0 flex flex-col items-center justify-center text-center z-10">
      <div class="max-w-lg px-4 sm:max-w-xl md:max-w-2xl">
        <!-- Split into two lines -->
        <h1 class="hero-title text-4xl sm:text-5xl md:text-6xl font-bold uppercase tracking-wide mb-4">
          <span ref="line1" class="inline-block opacity-0">Welcome to</span><br />
          <span ref="line2" class="inline-block opacity-0">Le Snacke</span>
        </h1>
        <p class="hero-subtitle text-lg sm:text-xl md:text-2xl mb-8 opacity-90">
          Savor exquisite flavors and unforgettable dining experiences in the heart of culinary delight.
        </p>
        <NuxtLink
            to="#menu"
            class="group inline-block bg-[#0A9987] text-white font-semibold py-3 px-6 rounded-lg relative overflow-hidden"
        >
          <span class="relative z-10">Explore Our Menu</span>
          <span class="absolute inset-0 bg-gradient-to-r from-teal-400 to-teal-600 translate-y-full group-hover:translate-y-0 transition-transform duration-300"></span>
        </NuxtLink>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";

const line1 = ref(null);
const line2 = ref(null);

onMounted(() => {
  gsap.fromTo(
      line1.value,
      { y: 50, opacity: 0 },
      { y: 0, opacity: 1, duration: 0.8, ease: "power3.out" }
  );
  gsap.fromTo(
      line2.value,
      { y: 50, opacity: 0 },
      { y: 0, opacity: 1, duration: 0.8, ease: "power3.out", delay: 0.3 }
  );
});
</script>

<style scoped>
@keyframes zoom-slow {
  0% { transform: scale(1.1); }
  100% { transform: scale(1); }
}
.animate-zoom-slow {
  animation: zoom-slow 10s ease-in-out infinite alternate;
}
</style>
