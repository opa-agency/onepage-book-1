<template>
  <div
    :class="[
      'relative px-4 py-16 sm:rounded-5xl sm:px-10 md:py-12 lg:px-12',
      featured && 'bg-blue-600 sm:shadow-lg',
    ]"
  >
    <div v-if="featured" class="absolute inset-0 mask-[linear-gradient(white,transparent)] text-white/10">
      <GridPattern x="50%" y="50%" />
    </div>
    <div class="relative flex flex-col">
      <h3
        :class="[
          'mt-7 text-lg font-semibold tracking-tight',
          featured ? 'text-white' : 'text-slate-900',
        ]"
      >
        {{ name }}
      </h3>
      <p
        :class="[
          'mt-2 text-lg tracking-tight',
          featured ? 'text-white' : 'text-slate-600',
        ]"
      >
        {{ description }}
      </p>
      <p class="order-first flex font-display font-bold">
        <span
          :class="[
            'text-[1.75rem]/9',
            featured ? 'text-blue-200' : 'text-slate-500',
          ]"
        >
          $
        </span>
        <span
          :class="[
            'mt-1 ml-1 text-7xl tracking-tight',
            featured ? 'text-white' : 'text-slate-900',
          ]"
        >
          {{ price }}
        </span>
      </p>
      <div class="order-last mt-8">
        <ul
          role="list"
          :class="[
            '-my-2 divide-y text-base tracking-tight',
            featured
              ? 'divide-white/10 text-white'
              : 'divide-slate-200 text-slate-900',
          ]"
        >
          <li v-for="feature in features" :key="feature" class="flex py-2">
            <CheckIcon
              :class="[
                'h-8 w-8 flex-none',
                featured ? 'fill-white' : 'fill-slate-600',
              ]"
            />
            <span class="ml-4">{{ feature }}</span>
          </li>
        </ul>
      </div>
      <Button
        :href="href"
        :color="featured ? 'white' : 'slate'"
        class="mt-8"
        :aria-label="`Get started with the ${name} plan for $${price}`"
      >
        Get started
      </Button>
    </div>
  </div>
</template>

<script setup>
import Button from './Button.vue'
import CheckIcon from './CheckIcon.vue'
import GridPattern from './GridPattern.vue'

defineProps({
  name: {
    type: String,
    required: true
  },
  description: {
    type: String,
    required: true
  },
  price: {
    type: String,
    required: true
  },
  features: {
    type: Array,
    required: true
  },
  href: {
    type: String,
    required: true
  },
  featured: {
    type: Boolean,
    default: false
  }
})
</script>
