<template>
  <section class="hero-section relative h-screen text-white overflow-hidden">
    <!-- Background Image -->
    <img
        src="https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=1920&q=80"
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
      <NuxtLink
          to="#menu"
          class="group inline-block bg-[#0A9987] text-white font-semibold py-3 px-6 rounded-lg relative overflow-hidden"
      >
        <span class="relative z-10">Explore Our Menu</span>
        <span
            class="absolute inset-0 bg-gradient-to-r from-teal-400 to-teal-600 translate-y-full group-hover:translate-y-0 transition-transform duration-300"
        ></span>
      </NuxtLink>
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
