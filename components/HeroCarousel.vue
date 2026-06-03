<script setup lang="ts">
import { ref, onMounted, onUnmounted } from 'vue'

const images = [
  { src: '/images/hero-1.jpg', alt: 'Gabriel at a rooftop venue at night' },
  { src: '/images/hero-2.jpg', alt: 'Demoing the robot to Mayor Adams at NYC City Hall' },
  { src: '/images/hero-3.jpg', alt: 'Gabriel looking out at the NYC skyline' },
  { src: '/images/hero-4.jpg', alt: 'Gabriel at an FTC robotics competition' },
]

const current = ref(0)
const paused = ref(false)
let timer: ReturnType<typeof setInterval> | null = null

function goTo(i: number) {
  current.value = i
}

onMounted(() => {
  timer = setInterval(() => {
    if (!paused.value) {
      current.value = (current.value + 1) % images.length
    }
  }, 3500)
})

onUnmounted(() => {
  if (timer) clearInterval(timer)
})
</script>

<template>
  <div
    class="relative w-full aspect-[4/5] rounded-3xl overflow-hidden select-none ring-1 ring-white/10"
    @mouseenter="paused = true"
    @mouseleave="paused = false"
  >
    <!-- All images stacked; active one is opacity-100 -->
    <img
      v-for="(img, i) in images"
      :key="img.src"
      :src="img.src"
      :alt="img.alt"
      class="absolute inset-0 w-full h-full object-cover transition-opacity duration-700"
      :class="current === i ? 'opacity-100' : 'opacity-0'"
      draggable="false"
    />

    <!-- Dot indicators -->
    <div class="absolute bottom-4 inset-x-0 flex justify-center gap-2">
      <button
        v-for="(_, i) in images"
        :key="i"
        class="w-1.5 h-1.5 rounded-full transition-all duration-300"
        :class="current === i ? 'bg-white scale-125' : 'bg-white/35 hover:bg-white/60'"
        :aria-label="`Image ${i + 1}`"
        @click="goTo(i)"
      />
    </div>
  </div>
</template>
