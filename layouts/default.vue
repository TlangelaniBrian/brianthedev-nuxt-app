<template>
  <div class="container mx-auto max-w-2xl">
    <header class="flex justify-between items-center mt-5">
      <div class=" flex items-center space-x-12">
        <div>
          <nuxt-link class="text-xl font-semibold p-2 hover:bg-gray-400"  to="/">Brian the Dev</nuxt-link>
        </div>
        <app-nav-menu/>
      </div>
      <client-only>
        <color-mode-selector/>
      </client-only>
    </header>
    <main class="p-2 mt-11">
    <slot />
    </main>
    <app-footer/>
  </div>
</template>
<script setup lang="ts">
useHead({
  htmlAttrs: {
    lang: 'en'
  },
  titleTemplate: 'Brian The Dev%s',
  link : [{
  rel:'preconnect',
  href: 'https://fonts.googleapi.com',
  },
    {
      rel: 'stylesheet',
      href: 'https://fonts.googleapis.com/css2?family=Roboto&display=swap'
    }
  ]
})
</script>
<style>
body {
  font-family: Roboto,sans-serif;
}
body {
  @apply bg-white dark:bg-gray-900 dark:text-gray-300;
}
</style>