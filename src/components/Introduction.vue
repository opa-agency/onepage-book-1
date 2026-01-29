<template>
  <section
    id="introduction"
    aria-label="Introduction"
    class="pt-20 pb-16 sm:pb-20 md:pt-36 lg:py-32"
  >
    <Container class="text-lg tracking-tight text-slate-700">
      <p class="font-display text-4xl font-bold tracking-tight text-slate-900">
        "Totul Începe cu un Pătrat" este o carte și un curs video care
        vă învață o metodă simplă de a desena pictograme pe care oricine o poate învăța.
      </p>
      <p class="mt-4">
        Înainte de a învăța cum să desenez pictograme, mi-am imaginat întotdeauna că
        sunt desenate manual folosind instrumentul pen, o tablă grafică elegantă,
        și ore și ore petrecute în reglarea manuală a curbelor Bezier.
      </p>
      <p class="mt-4">
        Dar se dovedește că nu așa funcționează designerii grozavi de pictograme.
      </p>
      <p class="mt-4">
        În "Totul Începe cu un Pătrat", veți învăța sistemele pe care experții
        le folosesc pentru a crea pictograme perfecte la pixel, fără să depindeți de mâna constantă.
      </p>
      <ul role="list" class="mt-8 space-y-3">
        <li v-for="feature in features" :key="feature" class="flex">
          <CheckIcon class="h-8 w-8 flex-none fill-blue-500" />
          <span class="ml-4">{{ feature }}</span>
        </li>
      </ul>
      <p class="mt-8">
        La sfârșitul cărții, veți avea toată încrederea de care aveți nevoie pentru a vă
        aprofunda și a începe să creați pictograme frumoase care se pot măsura cu
        oricare dintre seturile pe care le puteți găsi online.
      </p>
      <p class="mt-10">
        <a
          href="#free-chapters"
          class="text-base font-medium text-blue-600 hover:text-blue-800"
        >
          Obțineți două capitole gratuite direct la inbox
          <span aria-hidden="true">&rarr;</span>
        </a>
      </p>
    </Container>
  </section>
</template>

<script setup>
import CheckIcon from './CheckIcon.vue'
import Container from './Container.vue'

const features = [
  'Utilizarea operațiilor booleene pentru a combina forme de bază în pictograme complexe',
  'Cum să adaptați pictogramele la diferite dimensiuni',
  'Traducerea pictogramelor din stil contur în stil solid',
  'Identificarea caracteristicilor care fac un set de pictograme coerent',
  'Caracteristicile Figma și comenzile rapid de la tastatură pentru a-și accelera fluxul de lucru',
]
</script>
