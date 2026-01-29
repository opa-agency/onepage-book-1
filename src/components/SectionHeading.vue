<template>
  <h2
    :class="['inline-flex items-center rounded-full px-4 py-1 text-blue-600 ring-1 ring-blue-600 ring-inset']"
    v-bind="$attrs"
  >
    <span class="font-mono text-sm" aria-hidden="true">
      {{ number.toString().padStart(2, '0') }}
    </span>
    <span class="ml-3 h-3.5 w-px bg-blue-600/20" />
    <span class="ml-3 text-base font-medium tracking-tight">
      <slot></slot>
    </span>
  </h2>
</template>

<script setup>
defineProps({
  number: {
    type: [String, Number],
    required: true
  }
})
</script>
