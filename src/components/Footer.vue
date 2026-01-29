<template>
  <footer class="relative pt-5 pb-20 sm:pt-14 sm:pb-32">
    <div
      class="absolute inset-x-0 top-0 h-32 mask-[linear-gradient(white,transparent)] text-slate-900/10"
    >
      <GridPattern x="50%" />
    </div>
    <div class="relative text-center text-sm text-slate-600">
      <p>Drepturi de autor &copy; {{ currentYear }} Lindehoff Design, LLC</p>
      <p>Toate drepturile rezervate.</p>
    </div>
  </footer>
</template>

<script setup>
import GridPattern from './GridPattern.vue'

const currentYear = new Date().getFullYear()
</script>
