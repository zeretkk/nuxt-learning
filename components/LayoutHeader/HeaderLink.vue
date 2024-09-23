<script setup lang="ts">
defineProps<{
  href: string
  menu?: boolean
}>()
</script>

<template>
  <NuxtLink
    :to="href"
    class="full after:bg-white relative flex flex-row items-center px-2.5 text-sm transition-colors duration-150 before:absolute before:left-0 before:top-0 before:-z-10 before:block before:bg-purple before:transition-all before:duration-300 before:ease-out after:absolute after:bottom-[-2px] after:left-0 after:hidden after:h-[2px] after:w-full after:bg-purple hover:text-background sm:text-xl"
    :class="{
      'py-2.5 before:h-full before:w-0 hover:before:w-full': menu,
      'before:h-0 before:w-full hover:before:h-full hover:after:block': !menu,
    }"
  >
    <slot />
  </NuxtLink>
</template>
