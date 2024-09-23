<script setup lang="ts">
import HeaderLink from '~/components/LayoutHeader/HeaderLink.vue'
import MobileMenu from '~/components/LayoutHeader/MobileMenu.vue'

const appConfig = useAppConfig()
const theme = useCookie('theme', { watch: true })
const isOpen = useState('isMenuOpen', () => false)

const changeTheme = () => {
  theme.value = theme.value === 'dark' ? 'light' : 'dark'
}
</script>

<template>
  <header class="border-b-2 border-background dark:border-foreground">
    <div class="container flex flex-row items-stretch justify-between">
      <p class="font-heading relative bg-yellow px-2.5 py-1 text-3xl font-bold text-background">
        {{ appConfig.title }}
      </p>
      <button
        class="full after:bg-white relative flex flex-row items-center px-2.5 text-xl sm:hidden"
        @click="isOpen = !isOpen"
      >
        <Icon name="tabler:menu-2" />
      </button>
      <MobileMenu :isOpen="isOpen" @closeMenu="isOpen = false" />
      <nav class="hidden flex-row items-stretch self-stretch sm:flex">
        <HeaderLink href="/">Главная</HeaderLink>
        <HeaderLink href="/about">Информация</HeaderLink>
        <HeaderLink href="/">Блог</HeaderLink>
        <button
          class="full after:bg-white relative flex flex-row items-center px-2.5 text-xl transition-colors duration-150 before:absolute before:left-0 before:top-0 before:-z-10 before:block before:h-0 before:w-full before:bg-purple before:transition-all before:duration-300 before:ease-out after:absolute after:bottom-[-2px] after:left-0 after:hidden after:h-[2px] after:w-full after:bg-purple hover:text-background hover:before:h-full hover:after:block"
          @click="changeTheme"
        >
          <Icon :name="theme === 'dark' ? 'tabler:sun' : 'tabler:moon-stars'" />
        </button>
      </nav>
    </div>
  </header>
</template>
