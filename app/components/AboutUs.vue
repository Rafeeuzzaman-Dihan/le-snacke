<script setup>
import ExploreMenuBtn from "~/components/common/ExploreMenuBtn.vue";

const aboutText = `
Le Snacke is a culinary haven where taste meets passion.
We serve freshly prepared dishes crafted from the finest ingredients,
ensuring every bite is an unforgettable experience.
From classic comfort foods to unique gourmet creations, our menu has something for everyone.
`;
</script>

<template>
  <section id="about" class="py-10 md:py-12 px-6 bg-[#FEF1D8]">
    <div class="max-w-6xl mx-auto flex flex-col md:flex-row items-center md:items-start gap-12">

      <!-- Image -->
      <div class="md:w-1/2">
        <img
            src="https://images.unsplash.com/photo-1600891964599-f61ba0e24092?auto=format&fit=crop&w=800&q=80"
            alt="About us"
            class="w-full h-full object-cover rounded-3xl shadow-lg"
        />
      </div>

      <!-- Text -->
      <div class="md:w-1/2 text-center md:text-left">
        <h2 class="text-4xl md:text-5xl font-bold text-[#0A9987] mb-6">About Us</h2>
        <p class="text-gray-800 text-lg leading-relaxed mb-6">
          {{ aboutText }}
        </p>
        <ExploreMenuBtn />
      </div>

    </div>
  </section>
</template>
