<script setup lang="ts">
const props = defineProps<{ error: { statusCode: number; message: string } }>()
</script>

<template>
  <div class="min-h-screen bg-surface flex items-center justify-center px-6">
    <div class="text-center">
      <p class="font-mono text-accent text-6xl font-bold">{{ props.error.statusCode }}</p>
      <h1 class="mt-4 text-2xl font-bold text-white">
        {{ props.error.statusCode === 404 ? 'Page not found' : 'Something went wrong' }}
      </h1>
      <p class="mt-3 text-zinc-400">{{ props.error.message }}</p>
      <NuxtLink to="/" class="mt-8 btn-primary inline-flex">← Back to home</NuxtLink>
    </div>
  </div>
</template>
