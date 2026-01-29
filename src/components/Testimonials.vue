<template>
  <section class="py-8 sm:py-10 lg:py-16">
    <Container class="text-center">
      <h2 class="font-display text-4xl font-bold tracking-tight text-slate-900">
        Cuvinte frumoase de la clienții timpurii...
      </h2>
      <p class="mt-4 text-lg tracking-tight text-slate-600">
        Am lucrat cu un mic grup de clienți cu acces timpuriu pentru a mă asigura că
        tot conținutul din carte era exact ceea ce aveau nevoie. Iata ce au spus ei
        despre produsul final.
      </p>
    </Container>
    <ul
      role="list"
      class="mx-auto grid max-w-2xl grid-cols-1 gap-8 px-4 lg:max-w-7xl lg:grid-cols-3 lg:px-8 mt-16"
    >
      <li
        v-for="(column, columnIndex) in testimonials"
        :key="columnIndex"
      >
        <ul role="list">
          <li
            v-for="(testimonial, testimonialIndex) in column"
            :key="testimonialIndex"
            :class="[
              testimonialIndex === 0 && 'hidden lg:list-item',
              testimonialIndex > 0 && 'mt-8',
            ]"
          >
            <TestimonialCard :author="testimonial.author">
              {{ testimonial.content }}
            </TestimonialCard>
          </li>
        </ul>
      </li>
    </ul>
  </section>
</template>

<script setup>
import Container from './Container.vue'
import TestimonialCard from './TestimonialCard.vue'
import avatarImage3 from '@/images/avatars/avatar-3.png'
import avatarImage4 from '@/images/avatars/avatar-4.png'
import avatarImage5 from '@/images/avatars/avatar-5.png'
import avatarImage6 from '@/images/avatars/avatar-6.png'
import avatarImage7 from '@/images/avatars/avatar-7.png'
import avatarImage8 from '@/images/avatars/avatar-8.png'
import avatarImage9 from '@/images/avatars/avatar-9.png'
import avatarImage10 from '@/images/avatars/avatar-10.png'
import avatarImage11 from '@/images/avatars/avatar-11.png'

const testimonials = [
  [
    {
      content: "Stilul de predare al Mirei nu are egal. Totul a fost ușor de urmărit la fiecare pas.",
      author: { name: 'Antonio Littel', role: 'Dezvoltator Frontend', image: avatarImage3 },
    },
    {
      content: "Deși eram entuziast să înveț, am fost pesimist că nu voi fi niciodată suficient de bun pentru a desena propriile mele pictograme. M-am înșelat — această carte este tot ce am avut nevoie.",
      author: { name: 'Lynn Nolan', role: 'Specialist Marketing', image: avatarImage4 },
    },
    {
      content: "Am lucrat ca designer profesionist de pictograme de ani de zile și am învățat multși trucuri noi care mi-au îmbunătățit munca",
      author: { name: 'Krista Prosacco', role: 'Designer Profesionist', image: avatarImage9 },
    },
  ],
  [
    {
      content: "Fur un magazin de comerț electronic care vinde ursuleți gumati rari și nu am găsit niciodată o bună pictogramă de ursuleț. Acum pot desena una proprie în minute.",
      author: { name: 'Cameron Considine', role: 'Întreprenător', image: avatarImage7 },
    },
    {
      content: "Pachetul complet merită pentru videoclipurile de demolition hebdomadare singure. Am învățat atât de mult privatizandul cum Mira descompune alte pictograme și le recreaște de la zero.",
      author: { name: 'Regina Wisoky', role: 'Student Design', image: avatarImage11 },
    },
    {
      content: "Nu m-am așteptat să găsesc multă valoare în comunitate, dar acum sunt acolo cel puțin o oră în fiecare zi și învaț sfaturi de la alți designeri.",
      author: { name: 'Vernon Cummerata', role: 'Ing. UI', image: avatarImage8 },
    },
  ],
  [
    {
      content: "Nu am putut crede cu ce viteză se mișcă Mira în Figma comparativ cu propriul meu flux de lucru. Desenez pictograme mai exact în jumătatea timpului cu comenzile rapid pe care le-am învățat din videoclipurile ei.",
      author: { name: 'Steven Hackett', role: 'Instructor Bootcamp', image: avatarImage5 },
    },
    {
      content: "Nu m-am gândit niciodată că voi apăsa desenul de pictograme, dar folosind ideile din această carte, a devenit un mod grozav pentru mine să mă relaxez și să fiu creativ.",
      author: { name: 'Carla Schoen', role: 'Fondator Startup', image: avatarImage10 },
    },
    {
      content: "Tot ce pot spune este uau — aceasta este cu ușurință cea mai bună resursă de design de pictograme pe care o întâlnit vreodatuă.",
      author: { name: 'Leah Kiehn', role: 'Director Creative', image: avatarImage6 },
    },
  ],
]
</script>
