<template>
  <section class="py-8 sm:py-10 lg:py-16">
    <Container class="text-center">
      <h2 class="font-display text-4xl font-bold tracking-tight text-slate-900">
        Some kind words from early customers...
      </h2>
      <p class="mt-4 text-lg tracking-tight text-slate-600">
        I worked with a small group of early access customers to make sure all
        of the content in the book was exactly what they needed. Hears what
        they had to say about the finished product.
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
      content: "Mira's teaching style is second to none. Everything was easy to follow every step of the way.",
      author: { name: 'Antonio Littel', role: 'Frontend Developer', image: avatarImage3 },
    },
    {
      content: "Even though I was excited to learn, I was pessimistic that I wouldn't actually ever get good enough to design my own icons. I was wrong — this book is all I needed.",
      author: { name: 'Lynn Nolan', role: 'Growth Marketer', image: avatarImage4 },
    },
    {
      content: "I've been employed as a professional icon designer for years and still learned tons of new tricks that have made my work even better",
      author: { name: 'Krista Prosacco', role: 'Professional Designer', image: avatarImage9 },
    },
  ],
  [
    {
      content: "I run an ecommerce store selling rare vintage gummy bears and could never find a good gummy bear icon. Now I can design my own in minutes.",
      author: { name: 'Cameron Considine', role: 'Entrepreneur', image: avatarImage7 },
    },
    {
      content: "The complete package is worth it for the weekly teardown videos alone. I've learned so much watching Mira take apart other icons and recreate them from scratch.",
      author: { name: 'Regina Wisoky', role: 'Design Student', image: avatarImage11 },
    },
    {
      content: "I didn't expect to find a lot of value in the community but now I'm in there for at least an hour every day picking up tips from other designers.",
      author: { name: 'Vernon Cummerata', role: 'UI Engineer', image: avatarImage8 },
    },
  ],
  [
    {
      content: "I couldn't believe how fast Mira moved in Figma compared to my own workflow. I'm designing icons more accurately in half the time with the shortcuts I learned from her videos.",
      author: { name: 'Steven Hackett', role: 'Bootcamp Instructor', image: avatarImage5 },
    },
    {
      content: "I never thought I would enjoy designing icons but using the ideas in this book, it's become a great way for me to relax while still being creative.",
      author: { name: 'Carla Schoen', role: 'Startup Founder', image: avatarImage10 },
    },
    {
      content: "All I can say is wow — this is easily the best icon design resource I've ever encountered.",
      author: { name: 'Leah Kiehn', role: 'Creative Director', image: avatarImage6 },
    },
  ],
]
</script>
