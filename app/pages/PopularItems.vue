<template>
  <section id="popular" class="py-32 bg-[#FEF1D8] overflow-hidden relative">
    <div class="max-w-7xl mx-auto px-6 text-center">
      <h2 class="text-4xl md:text-5xl font-bold text-[#0A9987] mb-4">
        Our Popular Items
      </h2>
      <p class="text-gray-700 max-w-2xl mx-auto mb-16 text-lg">
        Handpicked favorites our guests love. Crafted with care, presented with style.
      </p>

      <!-- Cards Container -->
      <div
          class="flex flex-col md:flex-row justify-center items-center gap-10 md:gap-8"
          ref="cardsContainer"
      >
        <div
            v-for="(item, index) in items"
            :key="index"
            class="relative w-full md:w-1/3 bg-white rounded-3xl shadow-2xl overflow-hidden cursor-pointer perspective"
            @mousemove="onCardHover($event, index)"
            @mouseleave="onCardLeave(index)"
            ref="cardRefs"
        >
          <!-- Image -->
          <div class="relative overflow-hidden h-96">
            <img
                :src="item.image"
                :alt="item.name"
                class="w-full h-full object-cover rounded-3xl transition-transform duration-500"
            />
          </div>

          <!-- Content -->
          <div class="absolute bottom-6 left-6 right-6 text-left">
            <h3 class="text-2xl font-bold text-gray-900 mb-2">{{ item.name }}</h3>
            <p class="text-gray-600 mb-4">{{ item.description }}</p>
            <span class="inline-block bg-[#0A9987] text-white px-4 py-2 rounded-full font-semibold">
              ${{ item.price }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import gsap from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

const items = [
  {
    name: "Cheesy Burger Deluxe",
    description: "Juicy beef patty stacked with cheddar and fresh toppings.",
    price: 12,
    image:
        "https://images.unsplash.com/photo-1550547660-d9450f859349?auto=format&fit=crop&w=1200&q=80",
  },
  {
    name: "Signature Pasta",
    description: "Rich creamy sauce with herbs and a sprinkle of parmesan.",
    price: 15,
    image:
        "https://images.unsplash.com/photo-1603133872878-684f24b73f9d?auto=format&fit=crop&w=1200&q=80",
  },
  {
    name: "Classic Milkshake",
    description: "Refreshing blend of vanilla ice cream and fresh milk.",
    price: 6,
    image:
        "https://images.unsplash.com/photo-1551024709-8f23befc6f87?auto=format&fit=crop&w=1200&q=80",
  },
];

// Refs for GSAP
const cardsContainer = ref(null);
const cardRefs = ref([]);

// Staggered entrance animation
onMounted(() => {
  gsap.from(cardRefs.value, {
    scrollTrigger: {
      trigger: cardsContainer.value,
      start: "top 80%",
    },
    y: 100,
    opacity: 0,
    duration: 1,
    ease: "power4.out",
    stagger: 0.3,
  });
});

// Card hover tilt effect
const onCardHover = (e, index) => {
  const card = cardRefs.value[index];
  const rect = card.getBoundingClientRect();
  const x = e.clientX - rect.left;
  const y = e.clientY - rect.top;
  const centerX = rect.width / 2;
  const centerY = rect.height / 2;

  const rotateX = ((y - centerY) / centerY) * 8; // max 8deg
  const rotateY = ((x - centerX) / centerX) * 8;

  gsap.to(card, { rotateX: -rotateX, rotateY: rotateY, scale: 1.05, duration: 0.4, ease: "power3.out" });
};

const onCardLeave = (index) => {
  const card = cardRefs.value[index];
  gsap.to(card, { rotateX: 0, rotateY: 0, scale: 1, duration: 0.5, ease: "power3.out" });
};
</script>

<style scoped>
/* Perspective container for 3D tilt */
.perspective {
  perspective: 1000px;
}
</style>
