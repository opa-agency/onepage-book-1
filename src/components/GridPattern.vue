<template>
  <svg aria-hidden="true" class="absolute inset-0 h-full w-full">
    <defs>
      <pattern
        :id="patternId"
        width="128"
        height="128"
        patternUnits="userSpaceOnUse"
        v-bind="$attrs"
      >
        <path d="M0 128V.5H128" fill="none" stroke="currentColor" />
      </pattern>
    </defs>
    <rect width="100%" height="100%" :fill="`url(#${patternId})`" />
  </svg>
</template>

<script setup>
import { ref } from 'vue'

const patternId = ref(`pattern-${Math.random().toString(36).substr(2, 9)}`)
</script>
