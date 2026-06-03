# Gabriel Liberov — Portfolio

Personal portfolio site built with Nuxt 3, Tailwind CSS, and TypeScript.

## Stack

- **Framework:** [Nuxt 3](https://nuxt.com)
- **Styling:** [Tailwind CSS](https://tailwindcss.com) + [@tailwindcss/typography](https://tailwindcss.com/docs/typography-plugin)
- **Language:** TypeScript / Vue 3 Composition API

## Running locally

```bash
npm install
npm run dev
```

Opens at [http://localhost:3000](http://localhost:3000).

## Building for production

```bash
npm run build
npm run preview
```

## Project structure

```
pages/
  index.vue          # Home (hero, about, skills, teasers)
  projects.vue       # Projects page
  blog/
    index.vue        # Blog post listing
    growth-milestone.vue
    working-in-a-team.vue
    capstone-reflection.vue
layouts/
  default.vue        # Nav + footer shell
assets/css/
  tailwind.css       # Tailwind layers + component classes
```
