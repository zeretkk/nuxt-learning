<script setup lang="ts">
import LayoutHeader from '~/components/LayoutHeader/LayoutHeader.vue'
import LayoutFooter from '~/components/LayoutFooter.vue'
</script>

<template>
  <LayoutHeader />
  <div class="min-h-dvh">
    <slot />
  </div>
  <LayoutFooter />
</template>

<style scoped></style>
