<template>
  <nav class="fixed top-0 left-0 w-full z-50 bg-transparent px-6 py-4 flex justify-center">
    <ul class="flex gap-8 text-white font-semibold text-lg">
      <li v-for="link in navLinks" :key="link.id">
        <a
            :href="link.href"
            class="hover:text-[#0A9987] transition-colors duration-300"
        >
          {{ link.label }}
        </a>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
const navLinks = [
  { id: 1, label: "Home", href: "#hero" },
  { id: 2, label: "Popular Items", href: "#popular" },
  { id: 3, label: "Menu", href: "#menu" },
  { id: 4, label: "About Us", href: "#about" },
  { id: 5, label: "Visit Us", href: "#visit" },
];
</script>

<style scoped>
html {
  scroll-behavior: smooth; /* smooth scrolling */
}
</style>
