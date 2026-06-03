<script setup lang="ts">
useSeoMeta({
  title: 'Blog — Gabriel Liberov',
  description: 'Writing on robotics, software development, and growth as an engineer.',
})

const posts = [
  {
    slug: 'seaperch-internationals',
    title: 'From a Hello Kitty Robot to City Hall — My Journey Through STEM and Why It Matters',
    date: 'May 8, 2026',
    tag: 'Capstone',
    excerpt:
      `Starting with a tortoise-paced freshman bot and ending at NYC City Hall with Mayor Adams and a 1st place technical design report at SeaPerch Internationals — the story of accidentally becoming an advocate for Staten Island robotics.`,
  },
  {
    slug: 'ftc-2025',
    title: 'Wings, Wires, and Supers — What FTC Teamwork Actually Looks Like',
    date: 'May 22, 2026',
    tag: 'Robotics · Teamwork',
    excerpt:
      `How late nights, buffalo sauce, and a near-disastrous slide redesign taught me more about collaboration and communication than any class ever could — and how it led SITHS Saturn to the State Championship.`,
  },
  {
    slug: 'regents-prep',
    title: 'From Regents Prep to Levina — When Your Project Gets a Pivot',
    date: 'May 15, 2026',
    tag: 'Growth Milestones',
    excerpt:
      `What happens when New York cancels the Regents exams and the app you spent a year building suddenly has no purpose — and how a midnight TypeScript bug and a pivot became the best engineering lesson I got.`,
  },
]
</script>

<template>
  <div class="max-w-5xl mx-auto px-6 py-20">
    <div class="mb-16">
      <span class="section-tag">Writing</span>
      <h1 class="mt-4 text-4xl font-bold text-white">Blog</h1>
      <p class="mt-4 text-zinc-400 max-w-xl leading-relaxed">
        Three posts on robotics, real-world software development, and four years of growth at SITHS.
      </p>
    </div>

    <div class="space-y-6">
      <NuxtLink
        v-for="post in posts"
        :key="post.slug"
        :to="`/blog/${post.slug}`"
        class="block card group hover:glow cursor-pointer"
      >
        <div class="flex items-start justify-between gap-4 flex-wrap">
          <span class="text-xs font-mono text-accent bg-accent/10 px-2 py-0.5 rounded-full">{{ post.tag }}</span>
          <time class="text-xs text-zinc-500 font-mono shrink-0">{{ post.date }}</time>
        </div>
        <h2 class="mt-4 text-xl font-semibold text-white group-hover:text-accent transition-colors leading-snug">
          {{ post.title }}
        </h2>
        <p class="mt-3 text-sm text-zinc-400 leading-relaxed">{{ post.excerpt }}</p>
        <div class="mt-5 flex items-center gap-2 text-accent text-sm font-medium">
          Read post
          <svg class="w-4 h-4 group-hover:translate-x-1 transition-transform" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
          </svg>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>
