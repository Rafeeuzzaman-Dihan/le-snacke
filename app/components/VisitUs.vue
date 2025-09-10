<template>
  <section class="md:py-6 py-6 px-6 max-w-6xl mx-auto">
    <!-- Title & Subheading -->
    <div class="text-center mb-12">
      <h1 class="text-[36px] md:text-[40px] font-bold text-[#FEF1D8] mb-2">Visit Us</h1>
      <p class="text-gray-700 text-[16px] md:text-[22px] mx-auto">
        We’d love to welcome you to our restaurant. Find us below or reach out via social media.
      </p>
    </div>

    <!-- Two-column layout -->
    <div class="grid md:grid-cols-2 gap-12 items-start mb-12">
      <!-- Left side: Contact Info -->
      <div class="space-y-5 text-gray-800">
        <!-- Address -->
        <div>
          <p class="text-lg font-bold">Address:</p>
          <p class="text-sm">123 Main Street, Downtown, Dhaka, Bangladesh</p>
        </div>

        <!-- Phone -->
        <div>
          <p class="text-lg font-bold">Phone:</p>
          <p class="text-sm">+880 123 456 789</p>
        </div>

        <!-- Follow Us -->
        <div>
          <p class="text-lg font-bold">Follow Us:</p>
          <div class="flex gap-4 text-2xl mt-1">
            <a href="https://facebook.com" target="_blank" class="hover:text-[#FEF1D8]">
              <i class="pi pi-facebook"></i>
            </a>
            <a href="https://instagram.com" target="_blank" class="hover:text-[#FEF1D8]">
              <i class="pi pi-instagram"></i>
            </a>
          </div>
        </div>
      </div>

      <!-- Right side: Map -->
      <div class="w-full h-64 rounded-xl overflow-hidden shadow-lg">
        <iframe
            class="w-full h-full"
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3651.9026362453186!2d90.39882721543409!3d23.810331894601622!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3755b8b019d1f1ab%3A0x4f56f3a1f3a1a1b1!2sDhaka%2C%20Bangladesh!5e0!3m2!1sen!2sus!4v1694345612345!5m2!1sen!2sus"
            allowfullscreen
            loading="lazy"
            referrerpolicy="no-referrer-when-downgrade"
        ></iframe>
      </div>
    </div>

    <!-- Bottom divider line -->
    <div class="border-t border-gray-300 pt-4 text-center">
      <p class="text-gray-800 text-[14px]">© 2025 Le Snacke. All rights reserved.</p>
    </div>
  </section>
</template>

<script setup>
// Make sure PrimeIcons CSS is imported in your main entry file (main.js or main.ts)
</script>
