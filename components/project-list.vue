
<template>
  <p class="mb-10">Take a look at my GitHub Projects</p>

  <section v-if="status !== 'success'">Loading</section>
  <section v-else-if="error">Error Something Went Wrong ...Try again</section>
  <section v-else>
    <ul class="grid grid-cols-1 gap-4">
      <li v-for="project in myProjects" :key="project.id" class="hover:bg-gray-50 font-mono border border-gray-100 rounded-sm p-4">
        <a :href="project.html_url" target="_blank">
          <div class="flex items-center justify-between text-sm">
            <div class="text-xl font-semibold mb-2">{{ project.name }}</div>
            <div class="text-sm text-gray-500">{{ project.language }}</div>
          </div>
          <p class="text-sm">{{ project.description }}</p>
        </a>
      </li>
    </ul>
  </section>
</template>
<script setup lang="ts">
import type { Project } from '~/assets/types/Project';

const projects = ref<Project[]>([]);
const { error, status, data } = await useFetch('https://api.github.com/users/TlangelaniBrian/repos');

projects.value = data.value as Project[];
const myProjects = computed(() => projects.value.sort((a, b) => a.name.localeCompare(b.name)));
</script>