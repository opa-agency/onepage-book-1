<template>
  <div v-if="!expandable.isExpanded.value" class="mt-10 flex justify-center">
    <button
      type="button"
      class="flex items-center text-base font-medium tracking-tight text-slate-900 hover:text-slate-700"
      @click="handleClick"
    >
      <slot></slot>
      <svg
        aria-hidden="true"
        viewBox="0 0 24 24"
        class="ml-2 h-6 w-6"
      >
        <path
          d="m17 14-5 5-5-5M12 18.5V5"
          fill="none"
          stroke="currentColor"
          stroke-width="2"
          stroke-linecap="round"
          stroke-linejoin="round"
        />
      </svg>
    </button>
  </div>
</template>

<script setup>
import { inject } from 'vue'

const expandable = inject('expandable')

const handleClick = (e) => {
  e.preventDefault()
  expandable.expand(e)
}
</script>
