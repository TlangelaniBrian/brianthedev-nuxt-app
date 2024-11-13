<template>
<div>
  <h1 class="landing">
    This is Brian's Projects
  </h1>
</div>
</template>
<script setup lang="ts">
useSeoMeta({
  description: 'Personal projects by Brian',
  ogTitle: 'Brian The Dev',
  ogDescription: '[og:description]',
  ogImage: '[og:image]',
  ogUrl: '[og:url]',
  twitterTitle: '[twitter:title]',
  twitterDescription: '[twitter:description]',
  twitterImage: '[twitter:image]',
  twitterCard: 'summary'
})

useHead({
  htmlAttrs: {
    lang: 'en'
  }
})
</script>
<style scoped>

</style>