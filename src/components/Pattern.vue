<template>
  <svg aria-hidden="true" :width="width" :height="height" v-bind="$attrs">
    <defs>
      <symbol :id="`${id}-0`" :width="size" :height="size">
        <rect class="fill-blue-500" :width="size" :height="size" />
        <circle
          class="fill-blue-600"
          :cx="size / 2"
          :cy="size / 2"
          :r="size * (13 / 40)"
        />
      </symbol>
      <symbol :id="`${id}-1`" :width="size" :height="size">
        <circle
          class="fill-blue-300"
          :cx="size / 2"
          :cy="size / 2"
          :r="size / 2"
        />
        <rect
          class="fill-blue-600"
          :width="size / 2"
          :height="size / 2"
          :x="size / 4"
          :y="size / 4"
        />
      </symbol>
    </defs>
    <template v-for="(row, rowIndex) in pattern" :key="`row-${rowIndex}`">
      <use
        v-for="(shape, columnIndex) in row"
        :key="`${rowIndex}-${columnIndex}`"
        :href="`#${id}-${shape}`"
        :x="columnIndex * size + columnIndex * gapX"
        :y="rowIndex * size + rowIndex * gapY"
      />
    </template>
  </svg>
</template>

<script setup>
import { ref, computed } from 'vue'

const props = defineProps({
  size: {
    type: Number,
    default: 40
  },
  gapX: {
    type: Number,
    default: 16
  },
  gapY: {
    type: Number,
    default: 8
  },
  pattern: {
    type: Array,
    default: () => [
      [0, 1, 0, 1, 1, 0, 1, 0],
      [1, 0, 1, 1, 0, 0, 0, 1],
      [0, 1, 0, 1, 1, 0, 1, 0],
      [1, 0, 1, 1, 0, 0, 0, 1],
    ]
  }
})

const id = ref(`pattern-${Math.random().toString(36).substr(2, 9)}`)
const width = computed(() => props.pattern[0].length * props.size + (props.pattern[0].length - 1) * props.gapX)
const height = computed(() => props.pattern.length * props.size + (props.pattern.length - 1) * props.gapY)
</script>
