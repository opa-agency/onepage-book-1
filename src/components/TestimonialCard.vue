<template>
  <figure class="rounded-4xl p-8 shadow-md ring-1 ring-slate-900/5">
    <blockquote>
      <p class="testimonial-quote text-lg tracking-tight text-slate-900">
        <slot></slot>
      </p>
    </blockquote>
    <figcaption class="mt-6 flex items-center">
      <div class="overflow-hidden rounded-full bg-slate-50">
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
</template>

<script setup>
defineProps({
  author: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>
.testimonial-quote::before {
  content: '"';
}

.testimonial-quote::after {
  content: '"';
}
</style>
