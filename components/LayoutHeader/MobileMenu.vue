<script setup lang="ts">
defineProps<{
  isOpen: boolean
}>()
defineEmits(['closeMenu'])
</script>

<template>
  <transition
    enter-active-class="transition duration-200 ease-in"
    enter-from-class="translate-y-[-100%]"
    enter-to-class="translate-y-[0%]"
    leave-active-class="transition duration-200 ease-in"
    leave-from-class="translate-y-[0%]"
    leave-to-class="translate-y-[-100%]"
  >
    <div
      class="absolute left-0 top-0 flex h-dvh w-dvw flex-col bg-foreground p-2.5 dark:bg-background"
      v-if="isOpen"
    >
      <div class="flex flex-row justify-end">
        <button @click="$emit('closeMenu')" aria-label="Close">
          <Icon name="tabler:x" class="text-2xl" />
        </button>
      </div>
      <div class="flex flex-auto flex-col items-center justify-center gap-4">
        <NuxtLink @click="$emit('closeMenu')" class="text-2xl" to="/">Главная</NuxtLink>
        <NuxtLink @click="$emit('closeMenu')" class="text-2xl" to="/about">Информация</NuxtLink>
        <NuxtLink @click="$emit('closeMenu')" class="text-2xl" to="/articles">Блог</NuxtLink>
      </div>
    </div>
  </transition>
</template>

<style scoped></style>
