<script setup lang="ts">
useSeoMeta({
  title: 'Projects — Gabriel Liberov',
  description: 'Real software projects built by Gabriel Liberov — from production web apps to FTC robot code.',
})

interface BulletApproach {
  bullets: string[]
}

interface Project {
  id: string
  emoji: string
  title: string
  category: string
  org: string
  description: string
  problem: string
  approach: BulletApproach
  stack: string[]
  repo?: string
  demo?: string
  reflection?: string
}

const projects: Project[] = [
  {
    id: 'regents-prep',
    emoji: '📚',
    title: 'SITHS Regents Prep App',
    category: 'Production Web App',
    org: 'sitechtimes/regents-prep-app-frontend',
    description:
      `A full-featured study platform that helps SITHS students prepare for New York State Regents exams with practice questions, progress tracking, and subject breakdowns.`,
    problem:
      `SITHS students had no centralized, purpose-built tool for Regents prep. Study guides were scattered across PDFs and random websites, with no way to track what you'd covered or focus on your weak spots. The goal was to build something that students would actually use over generic study sites.`,
    approach: {
      bullets: [
        'Built on Nuxt 3 with SSR for fast first-paint on slow school devices — critical for students cramming the night before an exam.',
        'TypeScript throughout for type safety across a large, multi-contributor codebase.',
        'Pinia stores manage per-user session state (subject progress, question history) with persistence across page reloads.',
        'Question flow UX was rearchitected to give immediate, actionable feedback without losing session context.',
        'Monolithic components were broken into smaller, reusable units — easier to test and reason about independently.',
        'Vitest testing pipeline set up from scratch; caught three store-layer bugs on first run.',
        'Backend communication is environment-configured, keeping dev and production endpoints cleanly separated.',
      ],
    },
    stack: ['Nuxt 3', 'Vue 3', 'TypeScript', 'Tailwind CSS', 'Pinia', 'Vitest', 'ESLint'],
    repo: 'https://github.com/sitechtimes/regents-prep-app-frontend',
    demo: 'https://regents.siths.dev',
    reflection:
      `Working on a production codebase with 1,000+ commits and a real user base is a completely different experience from side projects. Code review feedback stings more when it's in front of teammates, and you think twice before merging something that real students will use. This project taught me what "production-ready" actually means.`,
  },
  {
    id: 'levina-llm',
    emoji: '🧠',
    title: 'Levina Language Model Frontend',
    category: 'AI Interface',
    org: 'sitechtimes/Levina-Language-Model-Frontend',
    description:
      `A chat interface for Levina, SITHS's in-house language model — built by repurposing the Regents Prep component library after New York State cancelled the Regents exams, and extending it with LLM-specific features like streaming output and conversation history.`,
    problem:
      `When New York State cancelled the Regents exams, the Regents Prep app lost its purpose. Rather than abandon the component library and infrastructure the team had built, we pivoted — repurposing the shared architecture to front a new project: Levina, SITHS's own language model. The challenge was identifying what transferred cleanly and what needed to be built from scratch for a fundamentally different product.`,
    approach: {
      bullets: [
        'Reused Regents Prep\'s Pinia store pattern, Tailwind design tokens, and base component structure as the foundation — avoided rebuilding from zero.',
        'Session management and user state logic carried over directly; conversation history maps cleanly onto the same persistence model as question-session progress.',
        'Replaced the question-flow UI with a streaming chat interface — responses are consumed via the Fetch API\'s ReadableStream and rendered token-by-token.',
        'New conversation components built on top of existing card and layout primitives, keeping visual consistency with the rest of the SITHS Times ecosystem.',
        'Error handling and loading states extended from Regents patterns to cover LLM-specific failure modes (timeouts, empty completions, rate limits).',
        'Middleware layer added to normalize the LLM API response format before it hits the store — keeps components decoupled from backend specifics.',
      ],
    },
    stack: ['Nuxt 3', 'Vue 3', 'TypeScript', 'Tailwind CSS', 'Pinia', 'Fetch ReadableStream'],
    repo: 'https://github.com/sitechtimes/Levina-Language-Model-Frontend',
  },
  {
    id: 'solar-telemetry',
    emoji: '☀️',
    title: 'Solar Car Telemetry Dashboard',
    category: 'Real-Time Dashboard',
    org: 'sitechtimes/Solar-Car-Telemetry-Frontend',
    description:
      `A real-time telemetry dashboard that visualizes live data from SITHS's solar car — speed, battery voltage, motor current, GPS position, and system health — streamed over WebSocket from the car's onboard computer.`,
    problem:
      `The solar car team needed a way to monitor the car's systems during a run without being physically connected to it. Engineers needed live data they could act on — not a CSV they'd look at afterward.`,
    approach: {
      bullets: [
        'WebSocket connection to the car\'s onboard backend streams telemetry frames in real time; the frontend reconnects automatically on drop.',
        'Incoming data is normalized in a central Pinia store before any component touches it — one source of truth, no per-component parsing.',
        'Speed and motor current are rendered as live line charts using a reactive chart component; the x-axis rolls forward as new frames arrive.',
        'Battery voltage is displayed as a gauge with color-coded thresholds (green → amber → red) so engineers can read system health at a glance without checking numbers.',
        'GPS coordinates are plotted on a map component that updates the car\'s position marker on every frame, giving a live track of the route.',
        'Each panel (speed, battery, GPS, motor) is a fully isolated Vue component — any panel can be removed or reconfigured without touching the others.',
      ],
    },
    stack: ['Vue 3', 'JavaScript', 'WebSockets', 'Chart.js', 'Leaflet.js', 'CSS'],
    repo: 'https://github.com/sitechtimes/Solar-Car-Telemetry-Frontend',
  },
  {
    id: 'ftc-code',
    emoji: '🤖',
    title: 'SITHS Saturn FTC — Decode',
    category: 'Robotics / Embedded',
    org: 'gliberov/SITHS-Saturn-FTC-Decode-2025-2026',
    description:
      `Java codebase for SITHS Saturn (Team 26195) for the 2025–2026 FTC Decode season. Built on Road Runner with a fully class-based subsystem architecture — a major structural step forward from the previous season.`,
    problem:
      `After our INTO THE DEEP rookie season, we had working code but a messy codebase — logic for the arm, claw, drivetrain, and intake were tangled together in OpModes. As Decode introduced new game elements and more complex robot interactions, we needed an architecture that let us develop and test each mechanism independently without breaking everything else.`,
    approach: {
      bullets: [
        'Each mechanical subsystem (drivetrain, arm, claw, intake, slides) is encapsulated in its own Java class with a defined interface — OpModes compose subsystems rather than re-implementing them.',
        'Subsystem classes own their hardware references, state machines, and safety checks internally; the OpMode only calls high-level commands like arm.extendTo(Position.HIGH).',
        'Road Runner handles all trajectory math for autonomous — spline paths with velocity and acceleration constraints, composed into action sequences that interleave movement and mechanism commands.',
        'MeepMeep used for offline trajectory visualization during autonomous design, cutting field-time tuning cycles significantly.',
        'Teleop driver bindings are mapped through a command layer — swapping a button remaps the command, never the subsystem logic underneath.',
        'Decode\'s game-specific scoring tasks are modeled as named action sequences, making it easy to chain or reorder scoring routines without rewriting path logic.',
      ],
    },
    stack: ['Java', 'FTC SDK', 'Road Runner', 'MeepMeep', 'Gradle'],
    repo: 'https://github.com/gliberov/SITHS-Saturn-FTC-Decode-2025-2026',
    reflection:
      `The class-based rewrite was the right call but painful early on. Extracting subsystems from tangled OpMode code meant touching everything at once. The payoff came mid-season when we could tune the arm without looking at drivetrain code, and add a new autonomous routine in an afternoon instead of a day.`,
  },
]
</script>

<template>
  <div class="max-w-5xl mx-auto px-6 py-20">
    <div class="mb-16">
      <span class="section-tag">Work</span>
      <h1 class="mt-4 text-4xl font-bold text-white">Projects</h1>
      <p class="mt-4 text-zinc-400 max-w-2xl leading-relaxed">
        Production apps, robotics code, and dev-team work from my time at SITHS.
        Hover each card to see a quick preview, or read the full breakdown below.
      </p>
    </div>

    <!-- Pinned repo preview grid -->
    <div class="grid sm:grid-cols-2 lg:grid-cols-4 gap-4 mb-20">
      <a
        v-for="project in projects"
        :key="project.id"
        :href="`#${project.id}`"
        class="group relative overflow-hidden bg-surface-1 border border-white/5 rounded-2xl p-5 hover:border-accent/40 transition-all duration-300 cursor-pointer"
      >
        <div class="transition-all duration-300 group-hover:opacity-0 group-hover:-translate-y-2">
          <span class="text-3xl">{{ project.emoji }}</span>
          <h3 class="mt-3 text-sm font-semibold text-white leading-snug">{{ project.title }}</h3>
          <p class="mt-1 text-xs text-zinc-500 font-mono truncate">{{ project.org }}</p>
        </div>
        <div class="absolute inset-0 p-5 flex flex-col justify-between opacity-0 translate-y-2 group-hover:opacity-100 group-hover:translate-y-0 transition-all duration-300 bg-surface-1">
          <div>
            <span class="text-xs font-mono text-accent">{{ project.category }}</span>
            <p class="mt-2 text-xs text-zinc-300 leading-relaxed line-clamp-4">{{ project.description }}</p>
          </div>
          <div class="flex flex-wrap gap-1.5 mt-3">
            <span v-for="s in project.stack.slice(0, 3)" :key="s" class="text-[10px] font-mono px-2 py-0.5 bg-surface-3 rounded-full text-zinc-400">
              {{ s }}
            </span>
          </div>
          <div class="mt-3 text-xs text-accent font-medium">Read more ↓</div>
        </div>
      </a>
    </div>

    <!-- Full project writeups -->
    <div class="space-y-16">
      <article v-for="project in projects" :id="project.id" :key="project.id">
        <div class="card hover:glow transition-all duration-300">

          <!-- Header -->
          <div class="flex items-start justify-between flex-wrap gap-4">
            <div class="flex items-center gap-4">
              <span class="text-4xl">{{ project.emoji }}</span>
              <div>
                <span class="section-tag">{{ project.category }}</span>
                <h2 class="mt-1 text-2xl font-bold text-white">{{ project.title }}</h2>
                <p class="mt-0.5 text-xs font-mono text-zinc-500">{{ project.org }}</p>
              </div>
            </div>
            <div class="flex items-center gap-3 flex-wrap">
              <a v-if="project.demo" :href="project.demo" target="_blank" rel="noopener" class="btn-primary text-xs py-1.5 px-3">
                Live Demo ↗
              </a>
              <a v-if="project.repo" :href="project.repo" target="_blank" rel="noopener" class="btn-ghost text-xs py-1.5 px-3">
                <svg class="w-3.5 h-3.5" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12 0C5.37 0 0 5.37 0 12c0 5.31 3.435 9.795 8.205 11.385.6.105.825-.255.825-.57 0-.285-.015-1.23-.015-2.235-3.015.555-3.795-.735-4.035-1.41-.135-.345-.72-1.41-1.23-1.695-.42-.225-1.02-.78-.015-.795.945-.015 1.62.87 1.845 1.23 1.08 1.815 2.805 1.305 3.495.99.105-.78.42-1.305.765-1.605-2.67-.3-5.46-1.335-5.46-5.925 0-1.305.465-2.385 1.23-3.225-.12-.3-.54-1.53.12-3.18 0 0 1.005-.315 3.3 1.23.96-.27 1.98-.405 3-.405s2.04.135 3 .405c2.295-1.56 3.3-1.23 3.3-1.23.66 1.65.24 2.88.12 3.18.765.84 1.23 1.905 1.23 3.225 0 4.605-2.805 5.625-5.475 5.925.435.375.81 1.095.81 2.22 0 1.605-.015 2.895-.015 3.3 0 .315.225.69.825.57A12.02 12.02 0 0 0 24 12c0-6.63-5.37-12-12-12z" />
                </svg>
                GitHub
              </a>
            </div>
          </div>

          <p class="mt-5 text-zinc-400 leading-relaxed">{{ project.description }}</p>

          <div class="mt-5 flex flex-wrap gap-2">
            <span v-for="s in project.stack" :key="s" class="skill-tag">{{ s }}</span>
          </div>

          <!-- Details grid -->
          <div class="mt-8 grid md:grid-cols-2 gap-6">
            <div class="bg-surface-2 rounded-xl p-5">
              <h3 class="text-sm font-semibold text-accent mb-3 flex items-center gap-2">
                <span>🎯</span> Problem & Purpose
              </h3>
              <p class="text-sm text-zinc-400 leading-relaxed">{{ project.problem }}</p>
            </div>
            <div class="bg-surface-2 rounded-xl p-5">
              <h3 class="text-sm font-semibold text-accent mb-3 flex items-center gap-2">
                <span>⚙️</span> Technical Approach
              </h3>
              <ul class="space-y-2">
                <li
                  v-for="(bullet, i) in project.approach.bullets"
                  :key="i"
                  class="flex items-start gap-2 text-sm text-zinc-400 leading-relaxed"
                >
                  <span class="text-accent mt-0.5 shrink-0">→</span>
                  <span>{{ bullet }}</span>
                </li>
              </ul>
            </div>
          </div>

          <div v-if="project.reflection" class="mt-4 bg-surface-2 rounded-xl p-5 border-l-2 border-accent/50">
            <h3 class="text-sm font-semibold text-white mb-2 flex items-center gap-2">
              <span>💡</span> Reflection
            </h3>
            <p class="text-sm text-zinc-400 leading-relaxed">{{ project.reflection }}</p>
          </div>

        </div>
      </article>
    </div>
  </div>
</template>
