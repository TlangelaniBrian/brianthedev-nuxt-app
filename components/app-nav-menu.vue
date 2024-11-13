<template>
  <nav class="font-mono">
    <ul class="flex space-x-4">
      <li class="link" v-for="{name, path} in getLinks()" :key="path">
        <nuxt-link class="p-1 hover:bg-grey-200" :to="path">{{ name }}</nuxt-link>
      </li>
    </ul>
  </nav>
</template>
<script setup lang="ts">
const links = ref([
  { name: 'About', path: '/about' },
  { name: 'Blog', path: '/blog' },
  { name: 'Projects', path: '/projects' }
]);

function getLinks() {
  return links.value;
}
</script>
<style scoped>

</style>