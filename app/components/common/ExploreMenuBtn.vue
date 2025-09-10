<script setup>
import { defineProps } from 'vue';

const props = defineProps({
  text: { type: String, default: 'Explore Our Menu' },
  to: { type: String, default: '#menu' }
});

const navigate = () => {
  const target = document.querySelector(props.to);
  if (target) {
    target.scrollIntoView({ behavior: 'smooth' });
  }
};
</script>

<template>
  <button
      @click="navigate"
      class="relative inline-block px-6 py-3 text-[16px] text-white rounded-lg overflow-hidden transition-all duration-300 group bg-[#0A9987] hover:bg-teal-600"
  >
    <span class="relative z-10">{{ text }}</span>
    <!-- Glow effect -->
    <span
        class="absolute inset-0 bg-gradient-to-r from-teal-400 to-teal-600 opacity-50 translate-x-[-100%] group-hover:translate-x-0 transition-transform duration-500"
    ></span>
  </button>
</template>
