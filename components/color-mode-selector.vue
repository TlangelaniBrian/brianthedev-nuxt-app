<template>
  <div class="flex justify-end space-x-4">
    <div v-if="showNextModeLable" class="text-s hover:bg-gray-100 dark:hover:bg-gray-800 rounded-lg">{{ nextMode }}</div>
    <button @mouseenter="showNextModeLable = true"
            @mouseleave="showNextModeLable = false"
            @click="toggleColorMode"
            > {{ nextModeIcon }}
    </button>
  </div>
</template>
<script setup lang="ts">
const showNextModeLable = ref(false);
const colorMode =  useColorMode();
const modes = ref(['system', 'dark','light']);
const nextModeIcons = ref({
  system: '🌓',
  dark: '🌑',
  light: '☀️',
});

const nextMode = computed(() => {
  const i = modes.value.indexOf(colorMode.preference);
  return modes.value[(i + 1) % modes.value.length];
});

const nextModeIcon = computed(() =>
    nextModeIcons.value[nextMode.value as keyof typeof nextModeIcons.value]);

function toggleColorMode () {
  colorMode.preference = nextMode.value;
}

</script>