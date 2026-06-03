<script setup lang="ts">
useSeoMeta({
  title: 'From Regents Prep to Levina — When Your Project Gets a Pivot',
  description: 'What happens when New York cancels the Regents exams and the app you spent a year building suddenly has no purpose — and how a pivot became the best engineering lesson I got.',
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
      <span class="section-tag">Growth Milestones</span>
      <h1 class="mt-4 text-4xl font-bold text-white leading-tight">
        From Regents Prep to Levina — When Your Project Gets a Pivot
      </h1>
      <div class="mt-4 flex items-center gap-4 text-sm text-zinc-500">
        <time>May 15, 2026</time>
        <span>·</span>
        <span>Gabriel Liberov</span>
        <span>·</span>
        <span>7 min read</span>
      </div>
    </header>

    <div class="prose prose-invert prose-zinc max-w-none prose-pre:bg-surface-2 prose-pre:border prose-pre:border-white/10 prose-code:text-accent prose-headings:text-white prose-a:text-accent">
      <p>
        An analog clock ticking is midnight music. I've tiptoed into my room, peanut butter cookies in hand, convinced sugar would help me tackle this stubborn bug. Were my object properties undefined, or was this the classic "if all else fails, blame the backend developers"? Neither — just a TypeScript error, and my celebration after fixing it may have accidentally woken up my parents.
      </p>

      <p>
        That bug came from the Physics Regents Prep App, the largest project I worked on during my junior year. I joined in its initial stages, watched a complete infrastructure revision from scratch, and contributed core features to its second version. By launch I had grown into the role of <strong>frontend manager</strong>. A few months later, we learned the Regents exams were being phased out entirely. Just like that, the project had an expiration date.
      </p>

      <h2>What the App Was Built On</h2>

      <p>
        The core of the Regents app was a Pinia store that managed everything: authentication, course data, and question state. Here's the real <code>useUserStore</code> from the repo — notice how much it tracks:
      </p>

      <pre><code>export const useUserStore = defineStore("userStore", () => {
  const isAuth = ref(false);
  const name = ref("");
  const userType = ref&lt;"student" | "teacher"&gt;("student");

  const studentCourses = ref&lt;StudentCourse[]&gt;([]);
  const teacherCourses = ref&lt;TeacherCourseNoAssignment[]&gt;([]);
  const studentCurrentCourse = ref&lt;StudentCourse&gt;();
  const teacherCurrentCourse = ref&lt;TeacherCourse&gt;();

  const currentQuestion = ref&lt;StaticQuestionInterface | DynamicQuestionInterface&gt;();
  const loadedTopics = ref&lt;Record&lt;number, TopicMapped&gt;&gt;({});
  const loadedTopicPaths = ref&lt;Record&lt;number, number[]&gt;&gt;({});
  const loadedQuestions = ref&lt;Record&lt;number, TopicQuestionInterface&gt;&gt;({});
  const totalQuestionCount = ref&lt;number&gt;(0);

  async function login(email: string, password: string) {
    const { data, error } = await tryRequestEndpoint&lt;LoginSuccess | LoginFailure&gt;(
      "auth/login/", "POST", { email, password }, true
    );
    if (!error && data && "name" in data) return handleLoginData(data);
    return data as LoginFailure;
  }

  // ...
});</code></pre>

      <p>
        The question-tracking refs (<code>currentQuestion</code>, <code>loadedTopics</code>, <code>loadedQuestions</code>) were Regents-specific. But <code>studentCourses</code>, <code>isAuth</code>, <code>login</code>, <code>logout</code> — that was pure infrastructure.
      </p>

      <h2>The Pivot to Levina</h2>

      <p>
        When the Regents were cancelled, instead of shelving the codebase, we started asking what was worth saving. The answer was most of it. The <code>useUserStore</code> auth flow, the API request utility <code>tryRequestEndpoint</code>, the component primitives, the Tailwind design tokens — none of that was exam-specific.
      </p>

      <p>
        That U-turn became <strong>Levina</strong> — a language model frontend named after my Russian teacher. We repurposed our test prep infrastructure for Russian language instruction, adding AI feedback on essay writing and audio phonetics. The seagull logo got an Ushanka.
      </p>

      <h2>What Transferred Directly</h2>

      <p>
        The clearest proof of the reuse is <code>JoinClass.vue</code> — the modal students use to enroll in a course with a 6-character code. It's the same component in both repos. Here it is from Levina, unchanged from Regents:
      </p>

      <pre><code>async function submit() {
  if (!joinCode.value) return;
  isLoading.value = true;
  isErrored.value = false;

  const { data: course, error } = await tryRequestEndpoint&lt;StudentCourse&gt;(
    `courses/student/join/${joinCode.value}/`, "POST"
  );
  isLoading.value = false;

  if (error) {
    isErrored.value = true;
    return;
  }

  course.assignments = [];
  studentCourses.value.splice(0, 0, course);
  isSuccess.value = true;

  setTimeout(() => {
    isSuccess.value = false;
    closeModal();
  }, 1500);
}</code></pre>

      <p>
        Same <code>tryRequestEndpoint</code> utility. Same <code>studentCourses</code> store ref. Same optimistic UI pattern — push the new course immediately, then close the modal. Zero rewriting.
      </p>

      <h2>What Had to Be Built New</h2>

      <p>
        The assignment sidebar in Levina needed to understand LLM-specific completion logic — not just "has every question been answered" but tracking whether a language model assignment was fully worked through. The <code>assignmentIsComplete</code> computed property from the real Levina <code>Sidebar.vue</code>:
      </p>

      <pre><code>const assignmentIsComplete = computed(() => {
  const questionInterfaces = Object.values(
    props.assignment.assignment.questionInterfaces
  );
  return (
    (props.assignment.assignment.isStatic &&
      questionInterfaces.length === props.assignment.assignment.numQuestions &&
      questionInterfaces.every((qi) =>
        qi.question.answers.some((answer) => answer.selected)
      )) ||
    props.assignment.questionsCompleted >= props.assignment.assignment.numQuestions
  );
});</code></pre>

      <p>
        The shape is familiar — it reads from the same store, uses the same prop contract — but the completion logic had to account for Levina's hybrid static/dynamic assignment model, which didn't exist in Regents.
      </p>

      <h2>What I Actually Learned</h2>

      <p>
        Through this project's timeline I explored computer science beyond the stereotypical programming sense. Adapting to unforeseen circumstances and persevering through problems proved the subject to me as a true form of engineering. It wasn't always about creation — sometimes just redirection.
      </p>

      <p>
        So — <em>zdravstvuyte!</em>
      </p>
    </div>
  </article>
</template>
