<script setup lang="ts">
import CarouselCards from '@/components//Carrousel.vue'

const realDelMonteCards = [
  {
    title: 'Descubre los rumbos del centro',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/centro.jpg', import.meta.url).href,
  },
  {
    title: 'Elabora tu paste',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/pastes.jpg', import.meta.url).href,
  },
  {
    title: 'La Peña del Zumate',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/zumate.jpg', import.meta.url).href,
  },
  {
    title: 'Mina de Acosta',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/mina.jpg', import.meta.url).href,
  },
]
</script>

<template>
  <section class="mt-10">
    <CarouselCards :items="realDelMonteCards" />
  </section>
</template>
