<script setup lang="ts">
const appConfig = useAppConfig()
</script>

<template>
  <footer class="border-t-2 border-background py-10 dark:border-foreground">
    <div class="container flex flex-col items-stretch gap-3 sm:flex-row sm:justify-between">
      <div class="sm: order-2 sm:-order-1">
        <p class="text-2xl">{{ appConfig.title }}</p>
        <p class="text-md text-caption">&copy; Kirill Stepkin {{ new Date().getFullYear() }}</p>
      </div>
      <div class="flex flex-col items-stretch">
        <a
          href="https://vk.com/kirillzeret"
          rel="noreferrer"
          target="_blank"
          class="hover:text-purple"
        >
          <div class="flex flex-row items-center gap-1.5">
            <Icon name="tabler:brand-vk" class="text-2xl" />
            <p class="text-lg">VKontakte</p>
          </div>
        </a>
        <a
          href="https://github.com/zeretkk"
          rel="noreferrer"
          target="_blank"
          class="hover:text-purple"
        >
          <div class="flex flex-row items-center gap-1.5">
            <Icon name="tabler:brand-github" class="text-2xl" />
            <p class="text-lg">GitHub</p>
          </div>
        </a>
      </div>
    </div>
  </footer>
</template>
