<template>
  <div>
    <Hero />
    <Introduction />
    <NavBar />
    <TableOfContents />
    <Testimonial
      id="testimonial-from-tommy-stroman"
      :author="{
        name: 'Tommy Stroman',
        role: 'Front-end developer',
        image: avatarImage1,
      }"
    >
      <p>
        "I didn't know a thing about icon design until I read this book. Now I
        can create any icon I need in no time. Great resource!"
      </p>
    </Testimonial>
    <Screencasts />
    <Testimonial
      id="testimonial-from-gerardo-stark"
      :author="{
        name: 'Gerardo Stark',
        role: 'Creator of Pandemicons',
        image: avatarImage2,
      }"
    >
      <p>
        "I've tried to create my own icons in the past but quickly got
        frustrated and gave up. Now I sell my own custom icon sets online."
      </p>
    </Testimonial>
    <Resources />
    <FreeChapters />
    <Pricing />
    <Testimonials />
    <Author />
    <Footer />
  </div>
</template>

<script setup>
import Hero from './components/Hero.vue'
import Introduction from './components/Introduction.vue'
import NavBar from './components/NavBar.vue'
import TableOfContents from './components/TableOfContents.vue'
import Testimonial from './components/Testimonial.vue'
import Screencasts from './components/Screencasts.vue'
import Resources from './components/Resources.vue'
import FreeChapters from './components/FreeChapters.vue'
import Pricing from './components/Pricing.vue'
import Testimonials from './components/Testimonials.vue'
import Author from './components/Author.vue'
import Footer from './components/Footer.vue'
import avatarImage1 from './images/avatars/avatar-1.png'
import avatarImage2 from './images/avatars/avatar-2.png'
</script>
