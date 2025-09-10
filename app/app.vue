<template>
    <NuxtLayout>
      <NuxtPage />
    </NuxtLayout>
</template>
<script setup>
useHead({
  title: 'Le Snacke',
  meta: [
    { name: 'description', content: 'Savor exquisite flavors and unforgettable dining experiences.' }
  ],
  link: [
    { rel: 'icon', type: 'image/x-icon', href: '/favicon.png' }
  ]
})
</script>