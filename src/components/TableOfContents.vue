<template>
  <section
    id="table-of-contents"
    aria-labelledby="table-of-contents-title"
    class="scroll-mt-14 py-16 sm:scroll-mt-32 sm:py-20 lg:py-32"
  >
    <Container>
      <SectionHeading number="1" id="table-of-contents-title">
        Cuprins
      </SectionHeading>
      <p class="mt-8 font-display text-4xl font-bold tracking-tight text-slate-900">
        Aruncați o privire la tot conținutul acoperit în carte. Totul pe care
        aveți nevoie să știți se află înăuntru.
      </p>
      <p class="mt-4 text-lg tracking-tight text-slate-700">
        "Totul Începe cu un Pătrat" este compus din 240 de pagini editate apretant,
        foarte vizuale, concepute pentru a vă învăța tot ce trebuie să știți
        despre designul de pictograme fără umplutură inutilă.
      </p>
      <ol role="list" class="mt-16 space-y-10 sm:space-y-16">
        <li v-for="[title, pages] in Object.entries(tableOfContents)" :key="title">
          <h3 class="font-display text-3xl font-bold tracking-tight text-slate-900">
            {{ title }}
          </h3>
          <ol
            role="list"
            class="mt-8 divide-y divide-slate-300/30 rounded-2xl bg-slate-50 px-6 py-3 text-base tracking-tight sm:px-8 sm:py-7"
          >
            <li
              v-for="[pageTitle, pageNumber] in Object.entries(pages)"
              :key="pageTitle"
              class="flex justify-between py-3"
              :aria-label="`${pageTitle} on page ${pageNumber}`"
            >
              <span class="font-medium text-slate-900" aria-hidden="true">
                {{ pageTitle }}
              </span>
              <span class="font-mono text-slate-400" aria-hidden="true">
                {{ pageNumber }}
              </span>
            </li>
          </ol>
        </li>
      </ol>
    </Container>
  </section>
</template>

<script setup>
import Container from './Container.vue'
import SectionHeading from './SectionHeading.vue'

const tableOfContents = {
  'Primii pași': {
    'Primii pași': 1,
    'Introducere în Figma': 15,
    'Configurarea primei planning': 20,
  },
  'Noțiuni fundamentale': {
    'Linii și umpleri': 21,
    'Puncte finale': 22,
    'Curbe Bezier': 26,
    'Proiectare pe grilă': 31,
    'Forme vectoriale': 45,
  },
  'Operații booleene': {
    'Combinarea formelor': 50,
    'Scăderea formelor': 57,
    'Intersectarea formelor': 66,
    'Aplatizare': 78,
  },
  'Optimizare pentru producție': {
    'Pregătire pentru SVG': 82,
    'Configurarea setărilor de export': 88,
    'Minificare și eliminare metadate': 95,
  },
}
</script>
