<template>
  <section id="popular" class="py-20 bg-[#FEF1D8]">
    <div class="max-w-7xl mx-auto px-6 text-center">
      <!-- Heading -->
      <h2 class="text-3xl md:text-4xl font-bold text-[#0A9987] mb-4">
        Our Popular Items
      </h2>
      <p class="text-gray-700 max-w-2xl mx-auto mb-12">
        Handpicked favorites our guests love. Crafted with care and served fresh.
      </p>

      <!-- Grid -->
      <div class="grid gap-8 sm:grid-cols-2 lg:grid-cols-3 xl:grid-cols-5">
        <div
            v-for="(item, index) in items"
            :key="index"
            class="bg-white rounded-3xl shadow-lg overflow-hidden transition-transform hover:-translate-y-1 hover:shadow-2xl"
        >
          <!-- Image -->
          <div class="relative overflow-hidden h-64">
            <img
                :src="item.image"
                :alt="item.name"
                class="w-full h-full object-cover"
            />
          </div>

          <!-- Content -->
          <div class="p-4 text-left">
            <h3 class="text-lg font-semibold text-gray-900 mb-1">{{ item.name }}</h3>
            <p class="text-gray-600 text-sm mb-2">{{ item.description }}</p>
            <span class="inline-block bg-[#0A9987] text-white px-3 py-1 rounded-full font-semibold">
              ${{ item.price }}
            </span>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script setup>
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
    description: "Rich creamy sauce with herbs and parmesan.",
    price: 15,
    image:
        "https://images.unsplash.com/photo-1606755962771-b36f35d7c60f?auto=format&fit=crop&w=1200&q=80",
  },
  {
    name: "Classic Milkshake",
    description: "Refreshing blend of vanilla ice cream and fresh milk.",
    price: 6,
    image:
        "https://images.unsplash.com/photo-1551024709-8f23befc6f87?auto=format&fit=crop&w=1200&q=80",
  },
  {
    name: "Grilled Sandwich",
    description: "Golden toasted sandwich with fresh veggies and cheese.",
    price: 8,
    image:
        "https://images.unsplash.com/photo-1599785209707-0d5c4a3aa0b0?auto=format&fit=crop&w=1200&q=80",
  },
  {
    name: "Vegan Salad Bowl",
    description: "Fresh seasonal greens with tangy vinaigrette.",
    price: 10,
    image:
        "https://images.unsplash.com/photo-1627308595229-7830a5c91f9f?auto=format&fit=crop&w=1200&q=80",
  },
];
</script>

<style scoped>
/* Clean design, hover effects handled by Tailwind */
</style>
