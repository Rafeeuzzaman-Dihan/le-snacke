<script setup lang="ts">
import HeroSection from "~/components/HeroSection.vue";
import PopularItems from "~/components/PopularItems.vue";
import Menu from "~/components/Menu.vue";
import AboutUs from "~/components/AboutUs.vue";
import VisitUs from "~/components/VisitUs.vue";
</script>

<template>
  <div>
    <HeroSection />
    <PopularItems />
    <Menu id="menu" />
    <AboutUs />
    <VisitUs />
  </div>
</template>
