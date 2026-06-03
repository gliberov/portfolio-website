<script setup lang="ts">
useSeoMeta({
  title: 'Gabriel Liberov — ECE & Robotics @ Georgia Tech',
  description: 'Personal portfolio of Gabriel Liberov — incoming ECE & Robotics student at Georgia Tech, FTC roboticist, and full-stack developer.',
})

const skills = {
  Languages: [
    { name: 'Python', icon: '🐍' },
    { name: 'JavaScript', icon: '🟨' },
    { name: 'TypeScript', icon: '🔷' },
    { name: 'Java', icon: '☕' },
    { name: 'HTML/CSS', icon: '🌐' },
    { name: 'SQL', icon: '🗄️' },
  ],
  Frameworks: [
    { name: 'Vue.js', icon: '💚' },
    { name: 'Nuxt 3', icon: '🟢' },
    { name: 'Tailwind CSS', icon: '🎨' },
    { name: 'Pinia', icon: '🍍' },
    { name: 'Vitest', icon: '🧪' },
    { name: 'ESLint / Prettier', icon: '✨' },
  ],
  'Robotics & Tools': [
    { name: 'FTC / Road Runner', icon: '🤖' },
    { name: 'Git & GitHub', icon: '🐙' },
    { name: 'VS Code', icon: '💙' },
    { name: 'Figma', icon: '🖌️' },
    { name: 'Linux', icon: '🐧' },
    { name: 'REST APIs', icon: '🔗' },
  ],
}

const featuredPosts = [
  { slug: 'seaperch-internationals', title: 'From a Hello Kitty Robot to City Hall — My Journey Through STEM', date: 'May 8, 2026', tag: 'Growth · Impact' },
  { slug: 'ftc-2025', title: 'Wings, Wires, and Supers — What FTC Teamwork Actually Looks Like', date: 'May 22, 2026', tag: 'Robotics · Teamwork' },
  { slug: 'regents-prep', title: 'From Regents Prep to Levina — When Your Project Gets a Pivot', date: 'May 15, 2026', tag: 'Dev · Reflection' },
]
</script>

<template>
  <div>
    <!-- Hero -->
    <section class="relative min-h-[92vh] flex items-center overflow-hidden">
      <!-- Background glows -->
      <div class="absolute inset-0 pointer-events-none">
        <div class="absolute top-1/4 left-1/4 w-[500px] h-[500px] bg-accent/10 rounded-full blur-[120px]" />
        <div class="absolute bottom-0 right-0 w-72 h-72 bg-indigo-500/5 rounded-full blur-3xl" />
      </div>

      <div class="max-w-5xl mx-auto px-6 py-24 relative w-full">
        <div class="flex flex-col-reverse md:flex-row items-center gap-12 md:gap-16">

          <!-- Left: text -->
          <div class="flex-1 animate-fade-up">
            <h1 class="mt-4 text-5xl md:text-6xl font-bold tracking-tight leading-none">
              <span class="gradient-text">Gabriel</span><br />
              <span class="text-zinc-200">Liberov</span>
            </h1>
            <p class="mt-6 text-lg text-zinc-400 max-w-md leading-relaxed">
              Incoming <span class="text-white font-medium">ECE &amp; Robotics</span> student at
              <span class="text-white font-medium">Georgia Tech</span>.
              I build robots, make full-stack web apps, and love the overlap between hardware and software.
              SITHS Class of 2026.
            </p>

            <div class="mt-8 flex flex-wrap gap-4">
              <NuxtLink to="/projects" class="btn-primary">
                View My Work
                <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M17 8l4 4m0 0l-4 4m4-4H3" />
                </svg>
              </NuxtLink>
              <NuxtLink to="/blog" class="btn-ghost">Read My Blog</NuxtLink>
            </div>

            <div class="mt-10 flex items-center gap-5">
              <a href="https://github.com/gliberov" target="_blank" rel="noopener" class="text-zinc-500 hover:text-white transition-colors" aria-label="GitHub">
                <svg class="w-5 h-5" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z" />
                </svg>
              </a>
              <a href="https://linkedin.com/in/gabriel-liberov-6973a3282" target="_blank" rel="noopener" class="text-zinc-500 hover:text-white transition-colors" aria-label="LinkedIn">
                <svg class="w-5 h-5" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433a2.062 2.062 0 01-2.063-2.065 2.064 2.064 0 112.063 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z" />
                </svg>
              </a>
              <a href="mailto:gliberov19@gmail.com" class="text-zinc-500 hover:text-white transition-colors" aria-label="Email">
                <svg class="w-5 h-5" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" d="M21.75 6.75v10.5a2.25 2.25 0 01-2.25 2.25h-15a2.25 2.25 0 01-2.25-2.25V6.75m19.5 0A2.25 2.25 0 0019.5 4.5h-15a2.25 2.25 0 00-2.25 2.25m19.5 0v.243a2.25 2.25 0 01-1.07 1.916l-7.5 4.615a2.25 2.25 0 01-2.36 0L3.32 8.91a2.25 2.25 0 01-1.07-1.916V6.75" />
                </svg>
              </a>
            </div>
          </div>

          <!-- Right: photo carousel -->
          <div class="w-full md:w-[340px] lg:w-[380px] shrink-0 animate-fade-in">
            <HeroCarousel />
          </div>

        </div>
      </div>

      <!-- Scroll hint -->
      <div class="absolute bottom-6 left-1/2 -translate-x-1/2 flex flex-col items-center gap-1.5 text-zinc-600 text-xs animate-bounce">
        <span>scroll</span>
        <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" d="M19 9l-7 7-7-7" />
        </svg>
      </div>
    </section>

    <!-- About -->
    <section id="about" class="py-24 border-t border-white/5">
      <div class="max-w-5xl mx-auto px-6">
        <span class="section-tag">About me</span>
        <div class="mt-6 grid md:grid-cols-2 gap-12 items-center">
          <div>
            <h2 class="text-3xl font-bold text-white leading-snug">
              Building at the intersection of<br />
              <span class="text-accent">robotics and software</span>
            </h2>
            <div class="mt-6 space-y-4 text-zinc-400 leading-relaxed">
              <p>
                I'm a graduating senior at Staten Island Technical High School (SITHS) heading to
                <span class="text-white font-medium">Georgia Tech</span> to study Electrical Engineering
                with a focus on robotics. My interests vary from autonomous systems to full-stack web development.
              </p>
              <p>
                At SITHS I co-founded and served as code lead for <span class="text-white font-medium">SITHS Saturn</span>,
                our FTC rookie team, built real production web apps such as
                <span class="text-white font-medium">SITHS Regents Prep App</span> and <span class="text-white font-medium">Levina Language Model</span> teams, and competed at
                <span class="text-white font-medium">SeaPerch Underwater Robotics Internationals</span> 2025.
              </p>
              <p>
                This portfolio captures four years of learning — the wins, the losses, and more wins.
              </p>
            </div>
          </div>

          <div class="grid grid-cols-2 gap-4">
            <!-- Georgia Tech -->
            <div class="card text-center">
              <img src="/images/GT.jpg" alt="Georgia Tech" class="h-12 w-auto object-contain mx-auto" />
              <div class="mt-2 text-lg font-bold text-accent">ECE &amp; Robotics</div>
            </div>

            <!-- SITHS + 4 years -->
            <div class="card text-center">
              <img src="/images/SITHS.jpg" alt="Staten Island Technical High School" class="h-12 w-auto object-contain mx-auto" />
              <div class="mt-2 text-lg font-bold text-accent">4+ Years of Advanced CS</div>
            </div>

            <!-- SITHS Saturn FTC -->
            <div class="card text-center">
              <img src="/images/saturn.jpg" alt="SITHS Saturn FTC Team 26195" class="h-12 w-auto object-contain mx-auto" />
              <div class="mt-2 text-lg font-bold text-accent">Team 26195</div>
            </div>

            <!-- RoboNation / SeaPerch -->
            <div class="card text-center">
              <img src="/images/Robonation.png" alt="RoboNation SeaPerch" class="h-12 w-auto object-contain mx-auto" />
              <div class="mt-2 text-lg font-bold text-accent">International SeaPerch Challenge 2025</div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills -->
    <section id="skills" class="py-24 border-t border-white/5">
      <div class="max-w-5xl mx-auto px-6">
        <span class="section-tag">Technical skills</span>
        <h2 class="mt-4 text-3xl font-bold text-white">What I work with</h2>

        <div class="mt-10 space-y-8">
          <div v-for="(items, category) in skills" :key="category">
            <h3 class="text-sm font-mono text-zinc-500 mb-4">{{ category }}</h3>
            <div class="flex flex-wrap gap-3">
              <span v-for="skill in items" :key="skill.name" class="skill-tag">
                <span>{{ skill.icon }}</span>
                {{ skill.name }}
              </span>
            </div>
          </div>
        </div>

        <div class="mt-12 p-6 bg-surface-1 rounded-2xl border border-white/5 flex items-center justify-between flex-wrap gap-4">
          <div>
            <p class="text-white font-medium">See my code in action</p>
            <p class="text-sm text-zinc-400 mt-1">Public projects, org contributions, and experiments live on GitHub.</p>
          </div>
          <a href="https://github.com/gliberov" target="_blank" rel="noopener" class="btn-primary">
            <svg class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor">
              <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z" />
            </svg>
            github.com/gliberov
          </a>
        </div>
      </div>
    </section>

    <!-- Featured Projects teaser -->
    <section class="py-24 border-t border-white/5">
      <div class="max-w-5xl mx-auto px-6">
        <div class="flex items-end justify-between mb-10">
          <div>
            <span class="section-tag">Projects</span>
            <h2 class="mt-2 text-3xl font-bold text-white">Selected work</h2>
          </div>
          <NuxtLink to="/projects" class="btn-ghost hidden md:inline-flex">All projects →</NuxtLink>
        </div>

        <div class="grid md:grid-cols-2 gap-6">
          <NuxtLink to="/projects#regents-prep" class="card group cursor-pointer">
            <div class="flex items-start justify-between">
              <span class="text-2xl">📚</span>
              <span class="text-xs font-mono text-accent bg-accent/10 px-2 py-0.5 rounded-full">Nuxt · TypeScript</span>
            </div>
            <h3 class="mt-4 text-white font-semibold text-lg group-hover:text-accent transition-colors">
              SITHS Regents Prep App
            </h3>
            <p class="mt-2 text-sm text-zinc-400 leading-relaxed">
              Study platform used by real SITHS sophomores studying physics to prepare for Regents exams.
            </p>
            <div class="mt-4 flex flex-wrap gap-2">
              <span class="skill-tag">Vue</span>
              <span class="skill-tag">Nuxt</span>
              <span class="skill-tag">TypeScript</span>
              <span class="skill-tag">Tailwind</span>
            </div>
          </NuxtLink>

          <NuxtLink to="/projects#ftc-code" class="card group cursor-pointer">
            <div class="flex items-start justify-between">
              <span class="text-2xl">🤖</span>
              <span class="text-xs font-mono text-accent bg-accent/10 px-2 py-0.5 rounded-full">Java · FTC</span>
            </div>
            <h3 class="mt-4 text-white font-semibold text-lg group-hover:text-accent transition-colors">
              SITHS Saturn FTC Robot Code
            </h3>
            <p class="mt-2 text-sm text-zinc-400 leading-relaxed">
              Autonomous and teleop code for Team 26195's DECODE season. Built on Road Runner for precise odometry tracking.
            </p>
            <div class="mt-4 flex flex-wrap gap-2">
              <span class="skill-tag">Java</span>
              <span class="skill-tag">Road Runner</span>
              <span class="skill-tag">FTC SDK</span>
            </div>
          </NuxtLink>
        </div>

        <div class="mt-6 md:hidden">
          <NuxtLink to="/projects" class="btn-ghost w-full justify-center">All projects →</NuxtLink>
        </div>
      </div>
    </section>

    <!-- Blog teaser -->
    <section class="py-24 border-t border-white/5">
      <div class="max-w-5xl mx-auto px-6">
        <div class="flex items-end justify-between mb-10">
          <div>
            <span class="section-tag">Blog</span>
            <h2 class="mt-2 text-3xl font-bold text-white">Latest writing</h2>
          </div>
          <NuxtLink to="/blog" class="btn-ghost hidden md:inline-flex">All posts →</NuxtLink>
        </div>

        <div class="space-y-4">
          <NuxtLink
            v-for="post in featuredPosts"
            :key="post.slug"
            :to="`/blog/${post.slug}`"
            class="flex items-center justify-between p-5 bg-surface-1 border border-white/5 rounded-xl hover:border-accent/30 transition-all duration-200 group"
          >
            <div class="flex items-center gap-4 min-w-0">
              <span class="shrink-0 text-xs font-mono text-accent bg-accent/10 px-2 py-0.5 rounded-full">{{ post.tag }}</span>
              <span class="text-white text-sm group-hover:text-accent transition-colors truncate">{{ post.title }}</span>
            </div>
            <span class="hidden md:block text-zinc-500 text-xs whitespace-nowrap ml-4">{{ post.date }}</span>
          </NuxtLink>
        </div>

        <div class="mt-6 md:hidden">
          <NuxtLink to="/blog" class="btn-ghost w-full justify-center">All posts →</NuxtLink>
        </div>
      </div>
    </section>
  </div>
</template>
