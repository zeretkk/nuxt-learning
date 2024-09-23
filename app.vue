<script setup lang="ts">
const theme = useCookie('theme', {
  default: () => 'dark',
  watch: true,
})
useHead({
  link: [
    { rel: 'preconnect', href: 'https://fonts.googleapis.com' },
    { rel: 'preconnect', href: 'https://fonts.gstatic.com' },
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&family=Rubik:ital,wght@0,300..900;1,300..900&display=swap',
    },
  ],
})
</script>
<template>
  <Html :class="theme">
    <Body class="min-h-dvh font-mono dark:bg-background dark:text-foreground">
      <NuxtLayout>
        <NuxtPage />
      </NuxtLayout>
    </Body>
  </Html>
</template>
