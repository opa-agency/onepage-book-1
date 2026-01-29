<template>
  <section
    id="resources"
    aria-labelledby="resources-title"
    class="scroll-mt-14 py-16 sm:scroll-mt-32 sm:py-20 lg:py-32"
  >
    <Container>
      <SectionHeading number="3" id="resources-title">
        Resources
      </SectionHeading>
      <p class="mt-8 font-display text-4xl font-bold tracking-tight text-slate-900">
        Tools and resources you can use to get started even faster and
        progress even further.
      </p>
      <p class="mt-4 text-lg tracking-tight text-slate-700">
        Design assets, icon teardowns, and a community of fellow icon
        designers where you can ask questions, get feedback, and accelerate
        your learning.
      </p>
    </Container>
    <Container size="lg" class="mt-16">
      <ol
        role="list"
        class="-mx-3 grid grid-cols-1 gap-y-10 lg:grid-cols-3 lg:text-center xl:-mx-12 xl:divide-x xl:divide-slate-400/20"
      >
        <li
          v-for="resource in resources"
          :key="resource.title"
          class="grid auto-rows-min grid-cols-1 items-center gap-8 px-3 sm:grid-cols-2 sm:gap-y-10 lg:grid-cols-1 xl:px-12"
        >
          <div class="relative h-48 overflow-hidden rounded-2xl shadow-lg sm:h-60 lg:h-40">
            <component :is="resource.image" />
          </div>
          <div>
            <h3 class="text-base font-medium tracking-tight text-slate-900">
              {{ resource.title }}
            </h3>
            <p class="mt-2 text-sm text-slate-600">
              {{ resource.description }}
            </p>
          </div>
        </li>
      </ol>
    </Container>
  </section>
</template>

<script setup>
import { h } from 'vue'
import Container from './Container.vue'
import SectionHeading from './SectionHeading.vue'
import abstractBackgroundImage from '@/images/resources/abstract-background.png'
import discordImage from '@/images/resources/discord.svg'
import figmaImage from '@/images/resources/figma.svg'
import videoPlayerImage from '@/images/resources/video-player.svg'

const resources = [
  {
    title: 'Figma icon templates',
    description: 'Perfectly structured templates for quickly designing new icons at dozens of common sizes.',
    image: () => h('div', { class: 'absolute inset-0 flex items-center justify-center bg-[radial-gradient(#2C313D_35%,#000)]' }, [
      h('img', { src: figmaImage, alt: '' })
    ]),
  },
  {
    title: 'Weekly icon teardowns',
    description: 'Weekly videos where we dissect and recreate beautiful icons we find on the web.',
    image: () => h('div', { class: 'absolute inset-0 flex items-center justify-center' }, [
      h('img', { class: 'absolute inset-0 h-full w-full object-cover', src: abstractBackgroundImage, alt: '' }),
      h('img', { class: 'relative', src: videoPlayerImage, alt: '' })
    ]),
  },
  {
    title: 'Community of icon designers',
    description: "A private Discord server where you can get help and give feedback on each others' work.",
    image: () => h('div', { class: 'absolute inset-0 flex items-center justify-center bg-[#6366F1]' }, [
      h('img', { src: discordImage, alt: '' })
    ]),
  },
]
</script>
