<template>
  <section
    id="introduction"
    aria-label="Introduction"
    class="pt-20 pb-16 sm:pb-20 md:pt-36 lg:py-32"
  >
    <Container class="text-lg tracking-tight text-slate-700">
      <p class="font-display text-4xl font-bold tracking-tight text-slate-900">
        "Everything Starts as a Square" is a book and video course that
        teaches you a simple method to designing icons that anyone can learn.
      </p>
      <p class="mt-4">
        Before I learned how to design icons myself, I always imagined that
        they were drawn by hand using the pen tool, some sort of fancy
        graphics tablet, and hours and hours spent manually fine-tuning bezier
        curves.
      </p>
      <p class="mt-4">
        But it turns out this isn't how great icon designers work at all.
      </p>
      <p class="mt-4">
        In "Everything Starts as a Square", you'll learn the systems experts
        use to create pixel perfect icons, without relying on a steady hand.
      </p>
      <ul role="list" class="mt-8 space-y-3">
        <li v-for="feature in features" :key="feature" class="flex">
          <CheckIcon class="h-8 w-8 flex-none fill-blue-500" />
          <span class="ml-4">{{ feature }}</span>
        </li>
      </ul>
      <p class="mt-8">
        By the end of the book, you'll have all the confidence you need to dig
        in and start creating beautiful icons that can hold their own against
        any of the sets you can find online.
      </p>
      <p class="mt-10">
        <a
          href="#free-chapters"
          class="text-base font-medium text-blue-600 hover:text-blue-800"
        >
          Get two free chapters straight to your inbox{' '}
          <span aria-hidden="true">&rarr;</span>
        </a>
      </p>
    </Container>
  </section>
</template>

<script setup>
import CheckIcon from './CheckIcon.vue'
import Container from './Container.vue'

const features = [
  'Using boolean operations to combine basic shapes into complex icons',
  'How to adapt icons to different sizes',
  'Translating icons from an outline style to a solid style',
  'Identifying the characteristics that make an icon set cohesive',
  'Figma features and keyboard shortcuts to speed up your workflow',
]
</script>
