<script setup lang="ts">
useSeoMeta({
  title: "Wings, Wires, and Supers — What FTC Teamwork Actually Looks Like",
  description: 'How late nights, buffalo sauce, and a near-disastrous slide redesign taught me more about teamwork than any class ever could.',
})
</script>

<template>
  <article class="max-w-2xl mx-auto px-6 py-20">
    <NuxtLink to="/blog" class="inline-flex items-center gap-2 text-sm text-zinc-500 hover:text-white transition-colors mb-12">
      <svg class="w-4 h-4" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24">
        <path stroke-linecap="round" stroke-linejoin="round" d="M7 16l-4-4m0 0l4-4m-4 4h18" />
      </svg>
      Back to blog
    </NuxtLink>

    <header class="mb-12">
      <span class="section-tag">Robotics · Teamwork</span>
      <h1 class="mt-4 text-4xl font-bold text-white leading-tight">
        Wings, Wires, and Supers — What FTC Teamwork Actually Looks Like
      </h1>
      <div class="mt-4 flex items-center gap-4 text-sm text-zinc-500">
        <time>May 22, 2026</time>
        <span>·</span>
        <span>Gabriel Liberov</span>
        <span>·</span>
        <span>7 min read</span>
      </div>
    </header>

    <BlogImage src="/images/Lab.jpg" alt="SITHS Saturn team working late in the robotics lab" />

    <div class="prose prose-invert prose-zinc max-w-none prose-pre:bg-surface-2 prose-pre:border prose-pre:border-white/10 prose-code:text-accent prose-headings:text-white prose-a:text-accent">
      <p>
        Nothing competes with the aroma of warm, juicy chicken on freezing winter nights in New York. When the sky turns pitch black by 5pm, I head to my school's local Wingstop and buy a few boxes for my friends back in the robotics lab. Between bites, our chatter rises over the hum of 3D printers and the scent of solder fumes, blending into the chaotic atmosphere that somehow makes the food taste better. Whether cracking jokes, studying for upcoming physics tests, or revealing our lives' greatest secrets, it's a pleasure to share a table covered in metal channels and buffalo sauce.
      </p>

      <p>
        SITHS Saturn — Team 26195, INTO THE DEEP season — was my rookie year as FTC code lead. And most of what I actually learned about teamwork happened not during matches, but during those dinners.
      </p>

      <h2>The Slide Redesign Debate</h2>

      <p>
        During one of these evening feasts, we found ourselves in a conundrum about redesigning the slide system on our robot. In the playoffs of our last competition, it had tipped over mid-match. Despite looking hilarious at the moment, it was a disaster we weren't looking to repeat.
      </p>

      <p>
        My teammates proposed relocating the slides from the front to the middle of the chassis for improved weight distribution. My response triggered a debate. I pride myself on being a good listener, but I was often conservative when it came to redesign suggestions — hesitant to risk delays that could compromise our coding schedule. After all, we were still missing a full autonomous program. If we followed through on major build changes, autonomous would go on hold.
      </p>

      <p>
        As the heat of the disagreement matched that of the wings, something shifted. I realized that establishing a strong foundation — getting the slide positioning right — was necessary before any further software improvements would even matter. A faster autonomous routine on a robot that tips over is worthless.
      </p>

      <p>
        I joked that I would concede my case, on the condition that the robot would be off-limits while I performed my coding magic in the final week. The negotiation settled into a sense of unity, laughter replacing tension as we started planning the new model. Splitting wings made it easier to compromise — we were bonding over the solution, not just arguing about the problem.
      </p>

      <h2>What I Was Actually Bad At</h2>

      <p>
        I came into this season thinking teamwork was primarily about splitting tasks cleanly and executing your slice. I was wrong. The harder part is communication — specifically, the kind that crosses the hardware-software boundary.
      </p>

      <p>
        When autonomous failed during practice, my first instinct was always to look at the code. Half the time the root cause was mechanical — a loose odometry pod, a slipping gear, a frame flex that didn't show up on the bench. We had to build a shared vocabulary between the build team and the software team before we could even diagnose problems efficiently. That took months.
      </p>

      <p>
        The slide debate forced me to sit with something uncomfortable: being right about the technical answer is only half the job. You also have to bring people with you. A decision the whole team understands and supports executes better than a perfect decision only one person believed in.
      </p>

      <h2>Supers</h2>

      <p>
        We won the <strong>Innovate Award</strong> at NYC Qualifier 2 for our approach to the claw and rapid prototyping — the 3D-printed mechanism that went through four iterations before it was reliable. Then at NYC Qualifier 6, we won the <strong>Inspire Award</strong>, the highest judged award in FTC, recognizing robot performance, outreach, and documentation together. That sent us to the NYC Super Qualifier.
      </p>

      <p>
        At Supers, we swept our playoff matches and qualified for the <strong>New York State FTC Championship</strong>. For a rookie team that had tipped over in the playoffs just months earlier, that felt like a different universe.
      </p>

      <BlogImage src="/images/SupersWinners.jpg" alt="SITHS Saturn at the NYC Super Qualifier" />

      <p>
        The robot didn't get there because of the code or the hardware in isolation. It got there because a group of people who disagreed about slide positioning found a way to keep moving forward together. That — not any single match result — is what I'm taking with me to Georgia Tech.
      </p>
    </div>
  </article>
</template>
