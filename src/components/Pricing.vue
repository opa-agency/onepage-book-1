<template>
  <section
    id="pricing"
    aria-labelledby="pricing-title"
    class="scroll-mt-14 pt-16 pb-8 sm:scroll-mt-32 sm:pt-20 sm:pb-10 lg:pt-32 lg:pb-16"
  >
    <Container>
      <SectionHeading number="4" id="pricing-title">
        Preț
      </SectionHeading>
      <p class="mt-8 font-display text-5xl font-extrabold tracking-tight text-slate-900 sm:text-6xl">
        Aleţi-vă pachetul
      </p>
      <p class="mt-4 max-w-xl text-lg tracking-tight text-slate-600">
        "Totul Începe cu un Pătrat" este disponibil în două pachete diferite
        așa că puteți alege cel potrivit pentru dumneavoastră.
      </p>
    </Container>
    <div class="mx-auto mt-16 max-w-5xl lg:px-6">
      <div class="grid bg-slate-50 sm:px-6 sm:pb-16 md:grid-cols-2 md:rounded-6xl md:px-8 md:pt-16 lg:p-20">
        <Plan
          name="Esențial"
          description="Punctul de plecare perfect dacă sunteti pe buget."
          price="15"
          href="#"
          :features="[
            'E-cartea de 240 de pagini',
            'Modele de pictograme Figma',
            'Acces la comunitate',
          ]"
        />
        <Plan
          :featured="true"
          name="Complet"
          description="Toate resursele de pictograme pe care le-aţi putea cere vreodatu."
          price="229"
          href="#"
          :features="[
            'E-cartea de 240 de pagini',
            'Modele de pictograme Figma',
            'Peste o oră de screencasts',
            'Descompuneri hebdomadare de pictograme',
            'Acces la comunitate',
          ]"
        />
      </div>
    </div>
  </section>
</template>

<script setup>
import Container from './Container.vue'
import SectionHeading from './SectionHeading.vue'
import Plan from './Plan.vue'
</script>
