<template>
  <section
    id="screencasts"
    aria-labelledby="screencasts-title"
    class="scroll-mt-14 py-16 sm:scroll-mt-32 sm:py-20 lg:py-32"
  >
    <Container>
      <SectionHeading number="2" id="screencasts-title">
        Screencasts
      </SectionHeading>
      <p class="mt-8 font-display text-4xl font-bold tracking-tight text-slate-900">
        Peste o oră de conținut video de înaltă calitate, pas cu pas, pentru a-și
        îmbunătăți fluxul de lucru de design de pictograme.
      </p>
      <p class="mt-4 text-lg tracking-tight text-slate-700">
        Învățați cum să desenați propriile pictograme într-o serie de screencasts
        care vă vor învăța tot ce trebuie să știți pentru a trece de la
        începător la expert în puțin mai mult de o oră.
      </p>
    </Container>
    <Container size="lg" class="mt-16">
      <ol
        role="list"
        class="grid grid-cols-1 gap-x-8 gap-y-10 [counter-reset:video] sm:grid-cols-2 lg:grid-cols-4"
      >
        <li v-for="video in videos" :key="video.title" class="[counter-increment:video]">
          <div
            class="relative flex h-44 items-center justify-center rounded-2xl px-6 shadow-lg"
            style="background-image: conic-gradient(from -49.8deg at 50% 50%, #7331FF 0deg, #00A3FF 59.07deg, #4E51FF 185.61deg, #39DBFF 284.23deg, #B84FF1 329.41deg, #7331FF 360deg)"
          >
            <div class="flex overflow-hidden rounded-sm shadow-sm">
              <img :src="video.image" alt="" />
            </div>
            <div class="absolute bottom-2 left-2 flex items-center rounded-lg bg-black/30 px-1.5 py-0.5 text-sm text-white [@supports(backdrop-filter:blur(0))]:bg-white/10 [@supports(backdrop-filter:blur(0))]:backdrop-blur-sm">
              <svg
                aria-hidden="true"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
                viewBox="0 0 16 16"
                class="h-4 w-4 fill-current stroke-current"
              >
                <path d="M6.75 10.25v-4.5L10.25 8l-3.5 2.25Z" />
                <circle cx="8" cy="8" r="6.25" fill="none" />
              </svg>
              <time
                :datetime="`${video.runtime.minutes}m ${video.runtime.seconds}s`"
                class="ml-2"
              >
                {{ video.runtime.minutes }}:{{ video.runtime.seconds.toString().padStart(2, '0') }}
              </time>
            </div>
          </div>
          <h3 class="mt-8 text-base font-medium tracking-tight text-slate-900 before:mb-2 before:block before:font-mono before:text-sm before:text-slate-500 before:content-[counter(video,decimal-leading-zero)]">
            {{ video.title }}
          </h3>
          <p class="mt-2 text-sm text-slate-600">{{ video.description }}</p>
        </li>
      </ol>
    </Container>
  </section>
</template>

<script setup>
import Container from './Container.vue'
import SectionHeading from './SectionHeading.vue'
import duotoneImage from '@/images/screencasts/duotone.svg'
import gridsImage from '@/images/screencasts/grids.svg'
import setupImage from '@/images/screencasts/setup.svg'
import strokesImage from '@/images/screencasts/strokes.svg'

const videos = [
  {
    title: 'Primii pași cu Figma',
    description: 'Familiarizează-vă cu interfața Figma, diferitele instrumente pe care le oferă și caracteristicile cele mai importante.',
    image: setupImage,
    runtime: { minutes: 16, seconds: 54 },
  },
  {
    title: 'Configurarea planșei dvs.',
    description: 'Învață cum să creezi un nou artboard și să configurezi grila și riglele dvs. pentru a desena pictograme.',
    image: gridsImage,
    runtime: { minutes: 9, seconds: 12 },
  },
  {
    title: 'Desenarea primei pictograme',
    description: 'Folosind forme de bază și operații booleene, învață cum să desenezi propria pictogramă de notificare de la zero.',
    image: strokesImage,
    runtime: { minutes: 23, seconds: 25 },
  },
  {
    title: 'Tehnici avansate de design',
    description: 'Învață tehnicile pe care trebuie să le cunoști pentru a adapta pictograma originală la un stil modern duoton.',
    image: duotoneImage,
    runtime: { minutes: 28, seconds: 44 },
  },
]
</script>
