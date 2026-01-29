<template>
  <section
    id="free-chapters"
    aria-label="Free preview"
    class="scroll-mt-14 bg-blue-600 sm:scroll-mt-32"
  >
    <div class="overflow-hidden lg:relative">
      <Container
        size="md"
        class="relative grid grid-cols-1 items-end gap-y-12 py-20 lg:static lg:grid-cols-2 lg:py-28 xl:py-32"
      >
        <Pattern class="absolute -top-32 left-0 w-full sm:-top-5 sm:left-3/4 sm:ml-8 sm:w-auto md:left-2/3 lg:right-2 lg:left-auto lg:ml-0 xl:right-auto xl:left-2/3" />
        <div>
          <h2 class="font-display text-5xl font-extrabold tracking-tight text-white sm:w-3/4 sm:text-6xl md:w-2/3 lg:w-auto">
            Obțineți capitolele de mostră gratuite
          </h2>
          <p class="mt-4 text-lg tracking-tight text-blue-200">
            Introduceți adresa de email și voi trimite un eșantion din carte
            conținând două dintre capitolele mele preferate.
          </p>
        </div>
        <form class="lg:pl-16" @submit.prevent>
          <h3 class="text-base font-medium tracking-tight text-white">
            Obțineți două capitole gratuite direct la inbox
            <span aria-hidden="true">&rarr;</span>
          </h3>
          <div class="mt-4 sm:relative sm:flex sm:items-center sm:py-0.5 sm:pr-2.5">
            <div class="relative sm:static sm:flex-auto">
              <input
                type="email"
                id="email-address"
                required
                aria-label="Adresa de email"
                placeholder="Adresa de email"
                class="peer relative z-10 w-full appearance-none bg-transparent px-4 py-2 text-base text-white placeholder:text-white/70 focus:outline-hidden sm:py-3"
              />
              <div class="absolute inset-0 rounded-md border border-white/20 peer-focus:border-blue-300 peer-focus:bg-blue-500 peer-focus:ring-1 peer-focus:ring-blue-300 sm:rounded-xl" />
            </div>
            <Button
              type="submit"
              color="white"
              class="mt-4 w-full sm:relative sm:z-10 sm:mt-0 sm:w-auto sm:flex-none"
            >
              Obține capitole gratuite
            </Button>
          </div>
        </form>
      </Container>
    </div>
  </section>
</template>

<script setup>
import Button from './Button.vue'
import Container from './Container.vue'
import Pattern from './Pattern.vue'
</script>
