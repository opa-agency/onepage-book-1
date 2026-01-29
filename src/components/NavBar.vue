<template>
  <div ref="navBarRef" class="sticky top-0 z-50">
    <!-- Mobile menu -->
    <div class="sm:hidden">
      <div
        :class="[
          'relative flex items-center px-4 py-3',
          !mobileMenuOpen &&
            'bg-white/95 shadow-sm [@supports(backdrop-filter:blur(0))]:bg-white/80 [@supports(backdrop-filter:blur(0))]:backdrop-blur-sm',
        ]"
      >
        <template v-if="!mobileMenuOpen">
          <span aria-hidden="true" class="font-mono text-sm text-blue-600">
            {{ String(mobileActiveIndex + 1).padStart(2, '0') }}
          </span>
          <span class="ml-4 text-base font-medium text-slate-900">
            {{ sections[mobileActiveIndex].title }}
          </span>
        </template>
        <button
          :class="[
            '-mr-1 ml-auto flex h-8 w-8 items-center justify-center',
            mobileMenuOpen && 'relative z-10',
          ]"
          @click="mobileMenuOpen = !mobileMenuOpen"
          aria-label="Comuta meniu navigare"
        >
          <span v-if="!mobileMenuOpen" class="absolute inset-0" />
          <svg
            aria-hidden="true"
            fill="none"
            stroke-width="2"
            stroke-linecap="round"
            stroke-linejoin="round"
            viewBox="0 0 24 24"
            class="h-6 w-6 stroke-slate-700"
          >
            <path
              :d="
                mobileMenuOpen
                  ? 'M17 7 7 17M7 7l10 10'
                  : 'm15 16-3 3-3-3M15 8l-3-3-3 3'
              "
            />
          </svg>
        </button>
      </div>
      <div
        v-if="mobileMenuOpen"
        class="absolute inset-x-0 top-0 bg-white/95 py-3.5 shadow-sm [@supports(backdrop-filter:blur(0))]:bg-white/80 [@supports(backdrop-filter:blur(0))]:backdrop-blur-sm"
      >
        <a
          v-for="(section, sectionIndex) in sections"
          :key="section.id"
          :href="`#${section.id}`"
          class="flex items-center px-4 py-1.5"
          @click="mobileMenuOpen = false"
        >
          <span aria-hidden="true" class="font-mono text-sm text-blue-600">
            {{ String(sectionIndex + 1).padStart(2, '0') }}
          </span>
          <span class="ml-4 text-base font-medium text-slate-900">
            {{ section.title }}
          </span>
        </a>
      </div>
      <div class="absolute inset-x-0 bottom-full z-10 h-4 bg-white" />
    </div>

    <!-- Desktop menu -->
    <div
      class="hidden sm:flex sm:h-32 sm:justify-center sm:border-b sm:border-slate-200 sm:bg-white/95 sm:[@supports(backdrop-filter:blur(0))]:bg-white/80 sm:[@supports(backdrop-filter:blur(0))]:backdrop-blur-sm"
    >
      <ol
        role="list"
        class="mb-[-2px] grid auto-cols-[minmax(0,15rem)] grid-flow-col text-base font-medium text-slate-900 [counter-reset:section]"
      >
        <li
          v-for="(section, sectionIndex) in sections"
          :key="section.id"
          class="flex [counter-increment:section]"
        >
          <a
            :href="`#${section.id}`"
            :class="[
              'flex w-full flex-col items-center justify-center border-b-2 before:mb-2 before:font-mono before:text-sm before:content-[counter(section,decimal-leading-zero)]',
              sectionIndex === activeIndex
                ? 'border-blue-600 bg-blue-50 text-blue-600 before:text-blue-600'
                : 'border-transparent before:text-slate-500 hover:bg-blue-50/40 hover:before:text-slate-900',
            ]"
          >
            {{ section.title }}
          </a>
        </li>
      </ol>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const sections = [
  {
    id: 'table-of-contents',
    title: 'Cuprins',
  },
  { id: 'screencasts', title: 'Screencasts' },
  { id: 'resources', title: 'Resurse' },
  { id: 'pricing', title: 'Preț' },
  { id: 'author', title: 'Autor' },
]

const navBarRef = ref(null)
const activeIndex = ref(null)
const mobileMenuOpen = ref(false)

const mobileActiveIndex = ref(0)

const updateActiveIndex = () => {
  if (!navBarRef.value) {
    return
  }

  let newActiveIndex = null
  let elements = sections
    .map(({ id }) => document.getElementById(id))
    .filter((el) => el !== null)
  let bodyRect = document.body.getBoundingClientRect()
  let offset = bodyRect.top + navBarRef.value.offsetHeight + 1

  if (window.scrollY >= Math.floor(bodyRect.height) - window.innerHeight) {
    activeIndex.value = sections.length - 1
    mobileActiveIndex.value = sections.length - 1
    return
  }

  for (let index = 0; index < elements.length; index++) {
    if (
      window.scrollY >=
      elements[index].getBoundingClientRect().top - offset
    ) {
      newActiveIndex = index
    } else {
      break
    }
  }

  activeIndex.value = newActiveIndex
  mobileActiveIndex.value = newActiveIndex === null ? 0 : newActiveIndex
}

onMounted(() => {
  updateActiveIndex()

  window.addEventListener('resize', updateActiveIndex)
  window.addEventListener('scroll', updateActiveIndex, { passive: true })
})

onUnmounted(() => {
  window.removeEventListener('resize', updateActiveIndex)
  window.removeEventListener('scroll', updateActiveIndex)
})
</script>
