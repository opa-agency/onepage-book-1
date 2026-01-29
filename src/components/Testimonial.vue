<template>
  <aside
    :id="id"
    :aria-label="`Testimonial from ${author.name}`"
    class="relative bg-slate-100 py-16 sm:py-32"
  >
    <div class="text-slate-900/10">
      <GridPattern x="50%" patternTransform="translate(0 80)" />
    </div>
    <Container size="xs" class="relative">
      <figure>
        <div class="flex text-slate-900 sm:justify-center">
          <StarRating />
        </div>
        <blockquote class="mt-10 font-display text-4xl font-medium tracking-tight text-slate-900 sm:text-center">
          <slot></slot>
        </blockquote>
        <figcaption class="mt-10 flex items-center sm:justify-center">
          <div class="overflow-hidden rounded-full bg-slate-200">
            <img
              class="h-12 w-12 object-cover"
              :src="author.image"
              alt=""
              width="48"
              height="48"
            />
          </div>
          <div class="ml-4">
            <div class="text-base/6 font-medium tracking-tight text-slate-900">
              {{ author.name }}
            </div>
            <div class="mt-1 text-sm text-slate-600">{{ author.role }}</div>
          </div>
        </figcaption>
      </figure>
    </Container>
  </aside>
</template>

<script setup>
import Container from './Container.vue'
import GridPattern from './GridPattern.vue'
import StarRating from './StarRating.vue'

defineProps({
  id: {
    type: String,
    required: true
  },
  author: {
    type: Object,
    required: true
  }
})
</script>
