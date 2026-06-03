<script setup lang="ts">
useSeoMeta({
  title: 'From a Hello Kitty Robot to City Hall — My Journey Through STEM and Why It Matters',
  description: 'Starting with a tortoise-paced freshman bot and ending at NYC City Hall with Mayor Adams and a 1st place technical design report at SeaPerch Internationals — the story of accidentally becoming an advocate for Staten Island robotics.',
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
      <span class="section-tag">Capstone</span>
      <h1 class="mt-4 text-4xl font-bold text-white leading-tight">
        From a Hello Kitty Robot to City Hall — My Journey Through STEM and Why It Matters
      </h1>
      <div class="mt-4 flex items-center gap-4 text-sm text-zinc-500">
        <time>May 8, 2026</time>
        <span>·</span>
        <span>Gabriel Liberov</span>
        <span>·</span>
        <span>8 min read</span>
      </div>
    </header>

    <BlogImage src="/images/HelloKItty.jpg" alt="Freshman year robotics final — the Hello Kitty STEM project" />

    <div class="prose prose-invert prose-zinc max-w-none prose-pre:bg-surface-2 prose-pre:border prose-pre:border-white/10 prose-code:text-accent prose-headings:text-white prose-a:text-accent">
      <p>
        My Hello Kitty-themed Intro to STEM final was far more horrific than it sounded. The goal was simple on paper: program a robot to navigate a self-directed obstacle course, use a servo to grab a ring, deliver it across the field, and return precisely to the starting line. In practice, this meant countless failed test runs, debugging stubborn motor encoders for hours, and calibrating a sonic sensor to avoid a conveniently placed garbage bin.
      </p>

      <p>
        "TEAM 13!" Mr. Henriques announced across the room. Sweating bullets, heart pounding, I meticulously aligned my bot's steel dowel above the marker. He gave the countdown, and I tapped the green PRIZM button.
      </p>

      <p>
        The thing was slow. Incredibly tortoise-like — my teacher named it the "five-minute crawl." If there was anyone to blame it was his floors; I had intentionally increased motion times to avoid skidding against the cracked surface. By the time it hooked onto the ring, I had quite the audience. Classmates crowded around until I shouted for them to step back, fearing the sonar would mistake them for obstacles.
      </p>

      <p>
        As it approached the drop-off zone, I closed my eyes. The ring barely landed within the target, and the class erupted. Mr. Henriques posted the footage to all his Google Classrooms. I had to hide my code flash drive as if it were Willy Wonka's golden ticket.
      </p>

      <p>
        That experience — enthralling and terrifying — cemented my love for robotics.
      </p>

      <h2>Into the Deep</h2>

      <p>
        Four years later, I was the founding code lead of SITHS Saturn, Team 26195, competing in the 2024–2025 FTC INTO THE DEEP season. The scale had changed — from a Hello Kitty obstacle course to a 12-foot competition field, from PRIZM blocks to Road Runner spline trajectories — but the same instinct was running underneath it all.
      </p>

      <p>
        We won the Innovate Award at NYC Qualifier 2, the Inspire Award at NYC Qualifier 6 — the highest judged award in FTC — and qualified for the New York State Championship out of the NYC Super Qualifier. At one point during the season, we broke the NYC single-match point record.
      </p>

      <BlogImage src="/images/SupersCompeting.jpg" alt="SITHS Saturn competing at the NYC Super Qualifier" />

      <h2>City Hall</h2>

      <p>
        The last place I expected my final score to land was in the hand of the city's mayor.
      </p>

      <p>
        Following our season, our team was invited to demonstrate our robot at NYC City Hall as part of an event hosted by Mayor Adams's office. This wasn't just a celebration — it landed in the middle of a debate among PSAL administrators about whether robotics should be classified as an official NYC sport. We were walking evidence in that argument.
      </p>

      <p>
        It was also deeply personal. Staten Island is often overshadowed by the citywide community. Throughout the season, we had focused on giving the borough a voice: mentoring local middle-school teams, hosting a scrimmage that drew NYC FIRST's attention, which eventually led to the first-ever Staten Island qualifier being organized at home for the following season.
      </p>

      <p>
        I never set out to be an advocate. I set out to dunk samples in buckets. By trying to win robot tournaments, I ended up building something bigger: a foundation for future islanders to do the same.
      </p>

      <BlogImage src="/images/CityHall.jpg" alt="Demoing the robot to Mayor Adams at NYC City Hall" />

      <h2>SeaPerch Internationals — Technical Design Report, 1st Place</h2>

      <p>
        Alongside FTC, I competed in SeaPerch — an underwater robotics program where teams build ROVs and compete in pool-based missions. The 2025 International SeaPerch Challenge drew 181 teams from four countries to the University of Maryland, College Park, themed around Environmental Monitoring: Coral Restoration.
      </p>

      <p>
        From architecting odometry path-tracking on the FTC team to refining tether connection on the SeaPerch ROV, I thrive in the diverse processes of electrical engineering. The two programs taught me the same lesson from different angles: precise systems require you to understand the physical world, not just the logical one.
      </p>

      <p>
        At Internationals, our team placed <strong>1st place for Technical Design Report</strong> — the written and presented document explaining our engineering decisions, design tradeoffs, and the connection between our ROV choices and the coral restoration theme. Standing in front of international judges and reconstructing months of reasoning under pressure is a different skill from building the thing itself. We had earned it.
      </p>

      <BlogImage src="/images/International.jpg" alt="SeaPerch team at the International SeaPerch Challenge at UMD" />

      <h2>What It All Adds Up To</h2>

      <p>
        I accidentally became an advocate for Staten Island robotics. Now entering college, I hope to transform that accidental advocacy into intentional initiative — identifying gaps, leveraging smaller opportunities, building things that create tangible impact for the next generation of engineers.
      </p>

      <p>
        It started with a tortoise-paced robot and a class that erupted when a ring barely landed in a target. I'll take that energy everywhere I go.
      </p>
    </div>
  </article>
</template>
