<template>
  <div :data-expanded="isExpanded ? '' : undefined">
    <slot :is-expanded="isExpanded" :expand="expand"></slot>
  </div>
</template>

<script setup>
import { ref, provide } from 'vue'

const isExpanded = ref(false)

const expand = (e) => {
  if (e) {
    e.preventDefault()
  }
  isExpanded.value = true
}

provide('expandable', {
  isExpanded,
  expand
})
</script>
